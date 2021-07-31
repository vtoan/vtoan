# Overview
## Authentication
* Is the process of ascertaining who a user is.

* Responsible create one or more **identities** (`claims`) for the current user. To providing the for `Authorization` to make permission decisions against.  

* One or more **Authentication methods** can be used in the application, each of which includes `Scheme name`, `Handlers` and their `Configuration options`. (are called `Authentication schemes`).

* `Claims` can be created from any user or identity data which can be issued using a `trusted` identity provider or ASP.NET Core Identity.

## Authorization
* Refers to the process that determines what a user is able to do.

* Authorization requires an authentication mechanism.

* ASP.NET Core authorization provides a simple, declarative role and a rich policy-based model.

# In-Deep
## Authentication scheme
`Scheme name` commonly is **string** type with **unique value**. Because when an action require authentication user, program will retrieve **scheme name** in **HTTP Request Header** and find **handler have scheme name matched**, this is registered in program.

Ex: In HTTP Request Header has a sharp `www-authenticate: bearer`, "bearer" is **scheme name**.

There are multiple `Authentication scheme` approaches to select which authentication handler is responsible for generating the correct set of `claims`.

If the default scheme is *not specified*, the scheme must be specified in the authorize attribute, otherwise, throw a *exception*.

An authentication scheme is a name which corresponds to:
* An authentication handler.

* Options for configuring that specific instance of the handler.

## Authentication handler
An authentication handler:
* Is a type that implements the behavior of a scheme.

* Is derived from `IAuthenticationHandler` or `AuthenticationHandler<TOptions>`.

* Has the primary responsibility to authenticate users.

Based on the authentication scheme's configuration and the incoming request context, authentication handlers:
* Construct `AuthenticationTicket` objects representing the user's identity if authentication is successful.

* Return 'no result' or 'failure' if authentication is unsuccessful.

* Have methods for challenge and forbid actions for when users attempt to access resources:
  * They are unauthorized to access (forbid).

  * When they are unauthenticated (challenge).

Have three main methods in ASP Core:
* `Authenticate` : responsible for constructing the user's identity based on request context. It returns an `AuthenticateResult` indicating whether authentication was successful and, if so, the user's identity in an authentication ticket.

* `Challenge` : invoked by `Authorization` when an unauthenticated user requests an endpoint that requires authentication.

* `Forbid` : called by `Authorization` when an authenticated user attempts to access a resource they are not permitted to access.

## Create an authentication scheme
https://joonasw.net/view/creating-auth-scheme-in-aspnet-core-2

# Reference:
https://stackoverflow.com/questions/21645323/what-is-the-claims-in-asp-net-identity
https://docs.microsoft.com/en-us/aspnet/core/security/authentication/?view=aspnetcore-5.0
https://joonasw.net/view/creating-auth-scheme-in-aspnet-core-2
https://docs.microsoft.com/en-us/aspnet/core/security/authorization/limitingidentitybyscheme?view=aspnetcore-5.0
