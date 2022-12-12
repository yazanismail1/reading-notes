# Permissions & Postgresql

>Authentication or identification by itself is not usually sufficient to gain access to information or code. For that, the entity requesting access must have authorization.

Together with authentication and throttling, permissions determine whether a request should be granted or denied access.

Permission checks are always run at the very start of the view, before any other code is allowed to proceed. Permission checks will typically use the authentication information in the request.user and request.auth properties to determine if the incoming request should be permitted.

Permissions are used to grant or deny access for different classes of users to different parts of the API.

The simplest style of permission would be to allow access to any authenticated user, and deny access to any unauthenticated user. This corresponds to the IsAuthenticated class in REST framework.

A slightly less strict style of permission would be to allow full access to authenticated users, but allow read-only access to unauthenticated users. This corresponds to the IsAuthenticatedOrReadOnly class in REST framework.

## How Permissions are determined

Permissions in REST framework are always defined as a list of permission classes.

Before running the main body of the view each permission in the list is checked. If any permission check fails, an exceptions.PermissionDenied or exceptions.NotAuthenticated exception will be raised, and the main body of the view will not run.

When the permission checks fail, either a "403 Forbidden" or a "401 Unauthorized" response will be returned.

## Object level permissions

REST framework permissions also support object-level permissioning. Object level permissions are used to determine if a user should be allowed to act on a particular object, which will typically be a model instance.

Object level permissions are run by REST framework's generic views when .get_object() is called. As with view level permissions, an exceptions.PermissionDenied exception will be raised if the user is not allowed to act on the given object.

If you're writing your own views and want to enforce object level permissions, or if you override the get_object method on a generic view, then you'll need to explicitly call the .check_object_permissions(request, obj) method on the view at the point at which you've retrieved the object.

This will either raise a PermissionDenied or NotAuthenticated exception, or simply return if the view has the appropriate permissions.

### Limitations of object level permissions

For performance reasons the generic views will not automatically apply object level permissions to each instance in a queryset when returning a list of objects.

Often when you're using object level permissions you'll also want to filter the queryset appropriately, to ensure that users only have visibility onto instances that they are permitted to view.

Because the get_object() method is not called, object level permissions from the has_object_permission() method are not applied when creating objects. In order to restrict object creation you need to implement the permission check either in your Serializer class or override the perform_create() method of your ViewSet class.

## API Reference

**AllowAny**

The AllowAny permission class will allow unrestricted access, regardless of if the request was authenticated or unauthenticated.

**IsAuthenticated**

The IsAuthenticated permission class will deny permission to any unauthenticated user, and allow permission otherwise.

**IsAdminUser**

The IsAdminUser permission class will deny permission to any user, unless user.is_staff is True in which case permission will be allowed.

**IsAuthenticatedOrReadOnly**

The IsAuthenticatedOrReadOnly will allow authenticated users to perform any request. Requests for unauthorised users will only be permitted if the request method is one of the "safe" methods; GET, HEAD or OPTIONS.

**DjangoModelPermissions**

This permission class ties into Django's standard django.contrib.auth model permissions. This permission must only be applied to views that have a .queryset property or get_queryset() method. Authorization will only be granted if the user is authenticated and has the relevant model permissions assigned. The appropriate model is determined by checking get_queryset().model or queryset.model.

**DjangoModelPermissionsOrAnonReadOnly**

Similar to DjangoModelPermissions, but also allows unauthenticated users to have read-only access to the API.

**DjangoObjectPermissions**

This permission class ties into Django's standard object permissions framework that allows per-object permissions on models. In order to use this permission class, you'll also need to add a permission backend that supports object-level permissions, such as django-guardian.

As with DjangoModelPermissions, this permission must only be applied to views that have a .queryset property or .get_queryset() method. Authorization will only be granted if the user is authenticated and has the relevant per-object permissions and relevant model permissions assigned.

**Custom permissions**

To implement a custom permission, override BasePermission and implement either, or both, of the following methods:

- has_permission(self, request, view)

- has_object_permission(self, request, view, obj)

The methods should return True if the request should be granted access, and False otherwise.

## Overview of access restriction methods

REST framework offers three different methods to customize access restrictions on a case-by-case basis. These apply in different scenarios and have different effects and limitations.

- queryset/get_queryset(): Limits the general visibility of existing objects from the database. The queryset limits which objects will be listed and which objects can be modified or deleted. The get_queryset() method can apply different querysets based on the current action.

- permission_classes/get_permissions(): General permission checks based on the current action, request and targeted object. Object level permissions can only be applied to retrieve, modify and deletion actions. Permission checks for list and create will be applied to the entire object type. (In case of list: subject to restrictions in the queryset.)

- serializer_class/get_serializer(): Instance level restrictions that apply to all objects on input and output. The serializer may have access to the request context. The get_serializer() method can apply different serializers based on the current action.

The following table lists the access restriction methods and the level of control they offer over which actions.

||queryset|permission_classes|serializer_class|
|---|---|---|---|
|Action: list|global|global|object-level*|
|Action: create|no|global|object-level|
|Action: retrieve|global|object-level|object-level|
|Action: update|global|object-level|object-level|
|Action: partial_update|global|object-level|object-level|
|Action: destroy|global|object-level|no|
|Can reference action in decision|no**|yes|no**|
|Can reference request  in decision|no**|yes|no|

*A Serializer class should not raise PermissionDenied in a list action, or the entire list would not be returned.

**The get_*() methods have access to the current view and can return different Serializer or QuerySet instances based on the request or action.

# Things I want to know more about

- Docker
- Django
- Flask
- SQL

# References

[1] <https://www.django-rest-framework.org/api-guide/permissions/#permissions>
