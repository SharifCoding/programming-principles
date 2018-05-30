![JWT](https://cdn.auth0.com/content/jwt/jwt-diagram.png)

## Introduction to JSON Web Tokens
___A JSON Web Token (JWT) is a JSON object that is defined in RFC 7519 as a safe way to represent a set of information between two parties. The token is composed of a header, a payload, and a signature..___

#### Introduction
JSON Web Token (JWT) is an open standard (RFC 7519) that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. This information can be verified and trusted because it is digitally signed. JWTs can be signed using a secret (with HMAC algorithm) or a public/private key pair using RSA.
1. Encrypted string issued by web server
2. Stored by client, typically in local storage
3. Web server signs token using a SECRET KEY
4. When token is sent back to server, can verify it using the secret key
5. If token is tampered with, verification will fail

A JWT consist of three parts separated by dots (.), which looks like the following.
```bash
xxxxx.yyyyy.zzzzz
```
- Header; consists of two parts: the type of the token, which is JWT, and the hashing algorithm.
- Payload; which contains the claims which are entity (typically, the user) and additional metadata.
- Signature; takes the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.

#### JSON Web Token Benefits:
<b>Compact:</b> Because of its size, it can be sent through an URL, POST parameter, or inside an HTTP header. Additionally, due to its size its transmission is fast.
<b>Self-contained:</b> The payload contains all the required information about the user, to avoid querying the database more than once.

[JWT (JSON Web Tokens)](https://jwt.io/)
[5 Easy Steps to Understanding JSON Web Tokens (JWT)](https://medium.com/vandium-software/5-easy-steps-to-understanding-json-web-tokens-jwt-1164c0adfcec)

#### [Return: Express README](../README.md)
