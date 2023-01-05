# Authentication

## What is authentication?

Authentication is the process of determining whether someone or something is, in fact, who or what it says it is. Authentication technology provides access control for systems by checking to see if a user's credentials match the credentials in a database of authorized users or in a data authentication server. In doing this, authentication assures secure systems, secure processes and enterprise information security.

There are several authentication types. For purposes of user identity, users are typically identified with a user ID, and authentication occurs when the user provides credentials such as a password that matches their user ID. The practice of requiring a user ID and password is known as single-factor authentication (SFA). In recent years, companies have strengthened authentication by asking for additional authentication factors, such as a unique code that is provided to a user over a mobile device when a sign-on is attempted or a biometric signature, like a facial scan or thumbprint. This is known as two-factor authentication (2FA).

Authentication factors can even go further than SFA, which requires a user ID and password, or 2FA, which requires a user ID, password and biometric signature. When three or more identity verification factors are used for authentication -- **for example,** a user ID and password, biometric signature and perhaps a personal question the user must answer -- **it is **called multifactor authentication (MFA).

## Why is authentication important in cybersecurity?

Authentication enables organizations to keep their networks secure by permitting only authenticated users or processes to gain access to their protected resources. This may include computer systems, networks, databases, websites and other network-based applications or services.

Once authenticated, a user or process is usually subjected to an authorization process to determine whether the authenticated entity should be permitted access to a specific protected resource or system. A user can be authenticated but not be given access to a specific resource if that user was not granted permission to access it.

The terms authentication and authorization are often used interchangeably. While they are often implemented together, they are two distinct functions. Authentication is the process of validating the identity of a registered user or process before enabling access to protected networks and systems. Authorization is a more granular process that validates that the authenticated user or process has been granted permission to gain access to the specific resource that has been requested. The process by which access to those resources is restricted to a certain number of users is called access control. The authentication process always comes before the authorization process.

## How does authentication work?

During authentication, credentials provided by the user are compared to those on file in a database of authorized users' information either on the local operating system server or through an authentication server. If the credentials entered match those on file and the authenticated entity is authorized to use the resource, the user is granted access. User permissions determine which resources the user gains access to and also any other access rights that are linked to the user, such as during which hours the user can access the resource and how much of the resource the user is allowed to consume.

## What is authentication used for?

User and process authentication are used to ensure that only authorized individuals or processes are allowed to access company IT resources. Depending on the use cases for which authentication is used, authentication can consist of either SFA, 2FA or MFA.

## What are authentication factors?

Authenticating a user with a user ID and a password is usually considered the most basic type of authentication, and it depends on the user knowing two pieces of information -- **the user **ID or username, and the password. Since this type of authentication relies on just one authentication factor, it is a type of SFA.

Strong authentication is a term that is typically used to describe a type of authentication that is more reliable and resistant to attack. Strong authentication typically uses at least two different types of authentication factors and often requires the use of strong passwords containing at least eight characters, a mix of small and capital letters, special symbols and numbers.

**Used authentication factors include the following:**

- **Knowledge factor.** The knowledge factor, or something you know, may be any authentication credentials that consist of information that the user possesses, including a personal identification number (PIN), a username, a password or the answer to a secret question.

- **Possession factor.** The possession factor, or something you have, may be any credential based on items that the user can own and carry with them, including hardware devices, like a security token or a mobile phone used to accept a text message or to run an authentication app that can generate a one-time password (OTP) or PIN.

- **Inherence factor.** The inherence factor, or something you are, is typically based on some form of biometric identification, including fingerprints or thumbprints, facial recognition, retina scan or any other form of biometric data.

- **Location factor.** Where you are may be less specific, but the location factor is sometimes used as an adjunct to the other factors. Location can be determined to reasonable accuracy by devices equipped with the Global Positioning System or with less accuracy by checking network addresses and routes. The location factor cannot usually stand on its own for authentication, but it can supplement the other factors by providing a means of ruling out some requests. For example, it can prevent an attacker located in a remote geographical area from posing as a user who normally logs in only from their home or office in the organization's home country.

- **Time factor.** Like the location factor, the time factor, or when you are authenticating, is not sufficient on its own, but it can be a supplemental mechanism for weeding out attackers who attempt to access a resource at a time when that resource is not available to the authorized user. It may also be used together with location. For example, if the user was last authenticated at noon in the U.S., an attempt to authenticate from Asia one hour later would be rejected based on the combination of time and location.

## Authentication vs. authorization

Authorization includes the process through which an administrator grants rights to authenticated users, as well as the process of checking user account permissions to verify that the user has been granted access to those resources. The privileges and preferences granted for an authorized account depend on the user's permissions, which are either stored locally or on an authentication server. The settings defined for all these environment variables are established by an administrator.

## What are the different types of authentication?

Traditional authentication depends on the use of a password file, in which user IDs are stored together with hashes of the passwords associated with each user. When logging in, the password submitted by the user is hashed and compared to the value in the password file. If the two hashes match, the user is authenticated.

This approach to authentication has several drawbacks, particularly for resources deployed across different systems. For one thing, attackers who are able to gain access to the password file for a system can use brute-force attacks against the hashed passwords to extract the passwords. In addition, this method would require multiple authentications for modern applications that access resources across multiple systems.

Password-based authentication weaknesses can be addressed to some extent with smarter usernames and passwords based on rules such as minimum length and complexity using capital letters and symbols. However, password-based authentication and knowledge-based authentication are more vulnerable than systems that require multiple independent methods.

**Other authentication methods include the following:**


- **2FA.** This type of authentication adds an extra layer of protection to the process by requiring users to provide a second authentication factor in addition to the password. 2FA systems often require the user to enter a verification code received via text message on a preregistered mobile phone or mobile device, or a code generated by an authentication application.

- **MFA.** This type of authentication requires users to authenticate with more than one authentication factor, including a biometric factor, such as a fingerprint or facial recognition; a possession factor, like a security key fob; or a token generated by an authenticator app.

- **OTP.** An OTP is an automatically generated numeric or alphanumeric string of characters that authenticates a user. This password is only valid for one login session or transaction and is typically employed for new users or for users who lost their passwords and are given an OTP to log in and change to a new password.

- **Three-factor authentication.** This type of MFA uses three authentication factors -- usually, a knowledge factor, such as a password, combined with a possession factor, such as a security token, and an inherence factor, such as a biometric.

- **Biometrics.** While some authentication systems depend solely on biometric identification, biometrics are usually used as a second or third authentication factor. The more common types of biometric authentication available include fingerprint scans, facial or retina scans, and voice recognition.


- **Mobile authentication.** Mobile authentication is the process of verifying users via their devices or verifying the devices themselves. This enables users to log into secure locations and resources from anywhere. The mobile authentication process involves MFA that can include OTPs, biometric authentication or Quick Response code

- **Continuous authentication.** With continuous authentication, instead of a user being either logged in or out, a company's application continually computes an authentication score that measures how sure it is that the account owner is the individual who is using the device.

- **Application programming interface (API) authentication.** The standard methods of managing API authentication are HTTP basic authentication, API keys and Open Authorization (OAuth).

## User authentication vs. machine authentication

Machines also need to authorize their automated actions within a network. Online backup services, patching and updating systems, and remote monitoring systems, such as those used in telemedicine and smart grid technologies, all need to securely authenticate to verify that it is the authorized system involved in an interaction and not a hacker.

Machine authentication can be carried out with machine credentials, similar to a user's ID and password but submitted by the device in question. Machine authentication may also use digital certificates issued and verified by a certificate authority as part of a public key infrastructure to prove identification while exchanging information over the internet.

With the increasing number of internet-enabled devices, reliable machine authentication is crucial to enable secure communication for home automation and other internet of things applications, where almost any entity may be made addressable and able to exchange data over a network. It is important to realize that each access point is a potential intrusion point. Each networked device needs strong machine authentication, and despite their normally limited activity, these devices must be configured for limited permissions access to restrict what can be done even if they are breached.

# Things I want to know more about

- Cyber Security

# References

[1] <https://www.techtarget.com/searchsecurity/definition/authentication>
