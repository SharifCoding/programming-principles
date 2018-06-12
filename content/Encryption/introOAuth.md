![OAuth](https://cdn2.auth0.com/docs/media/articles/getting-started/overview.png)

## OAuth - Open standard for Oauthrization
___OAuth is an open protocol to allow secure Oauthrization in a simple and standard method from web, mobile, and desktop applications.___

OAuth is a standard that applications can use to provide client applications with “secure delegated access”. OAuth works over HTTP and Oauthrizes Devices, APIs, Servers and Applications with access tokens rather than credentials.

There are two versions of OAuth: OAuth 1.0a (no longer supported) and OAuth 2. These specifications are completely different from one another, and cannot be used together: there is no backwards compatibility between them.

#### OAuth 1.0a
`OAuth 1.0a` provides a method to access a protected resource at the provider, on behalf of the resource owner (the user). This process consists of the following steps:
1. The client obtains an unOauthrized request token.
2. The client redirects the user to a login dialog at the provider.
3. The user Oauthrizes the request token, associating it with their account.
4. The provider redirects the user back to the client.
5. The client exchanges the request token for an access token.
6. The access token allows the client to access a protected resource at the provider, on behalf of the user.

#### OAuth 2.0
`OAuth 2.0` is similar to the OAuth 1.0a protocol, but the steps to be followed are different:
1. The client redirects the user to a login dialog at the provider.
2. The user Oauthrizes the client.
3. The provider redirects the user back to the client, additionally returning an access_token.
4. The client validates the access token.
5. The access token allows the client to access a protected resource at the provider.

There are 4 separate modes of OAuth, which are called grant types. Each mode serves a different purpose, and is used in a different way. Depending on what type of service you are building, you might need to use one or more of these grant types to make stuff work.

#### 1. The OAuthrization Code Grant Type
The Oauthrization code OAuth grant type is meant to be used on web servers. You’ll want to use the Oauthrization code grant type if you are building a web application with server-side code that is NOT public. If you want to implement an OAuth flow in a server-side web framework like Express.js, Flask, Django, Ruby on Rails, an OAuthrization Code is the way to go.

#### 2. The Implicit Grant Type
The implicit grant type is meant to be used for client-side web applications (like React.js or Angular.js) that don’t have a server-side component — or any sort of mobile application that can use a mobile web browser.

Implicit grants are ideal for client-side web applications and mobile apps because this grant type doesn’t require you to store any secret key information at all — this means you can log someone into your site / app WITHOUT knowing what your application’s client_secret is.

#### 3. The Password Credentials Grant Type
The password credentials grant type is meant to be used for first class web applications OR mobile applications. This is ideal for official web and mobile apps for your project because you can simplify the Oauthrization workflow by ONLY asking a user for their username and password, as opposed to redirecting them to your site, etc.

#### 4. The Client Credentials Grant Type
The client credentials grant type is meant to be used for application code.

You’ll want to use the client credentials grant type if you are building an application that needs to perform non-user related tasks. For instance, you might want to update your application’s metadata — read in application metrics (how many users have logged into your service?) — etc.

[Auth0 Overview](https://auth0.com/docs/getting-started/overview)

#### [Return: Express README](../../README.md)
