# API

> One side of programming is connecting people together, well using APIs can do it and we don't need to reinvent the wheel that's why it is important to get to know how to send, get, update and delete data.

---
---

**What does REST stand for?**

Representational State Transfer (REST) as an architectural approach to designing web services. REST is an architectural style for building distributed systems based on hypermedia. REST is independent of any underlying protocol and is not necessarily tied to HTTP.

**REST APIs are designed around a _resources_.**

**What is an identifier of a resource? Give an example.**

is a URI that uniquely identifies that resource.https://adventure-works.com/orders/1

**What are the most common HTTP verbs?**

GET, POST, PUT, PATCH, and DELETE.

**What should the URIs be based on?**

resources.

**Give an example of a good URI.**

https://adventure-works.com/orders.

**What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?**

An API which makes alot of requests and it is bad.

**What status code does a successful GET request return?**

status code 200 (OK)

**What status code does an unsuccessful GET request return?**

If the resource cannot be found, the method should return 404 (Not Found).

**What status code does a successful POST request return?**

status code 201 (Created).

**What status code does a successful DELETE request return?**

If the delete operation is successful, the web server should respond with HTTP status code 204 (No Content), indicating that the process has been successfully handled, but that the response body contains no further information. If the resource doesn't exist, the web server can return HTTP 404 (Not Found).

---
---

## Things I want to know more about

- webpack
- APIs
- CRUD
- Type of requests

 ---

## References

[1]  25/07/2022, _RESTful web API design_, microsoft.com, accessed 30 August 2022, <https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design>
