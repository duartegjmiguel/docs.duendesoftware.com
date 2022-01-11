---
title: "User Interaction"
weight: 20
---

These samples illustrate customization of the [interactive pages]({{< ref "/ui" >}}) used in your IdentityServer.

### SPA-style login page
This sample shows an example of building the interactive pages (login, consent, logout, and error) as client-rendered (typical of SPAs), rather than server-rendered. Since there are many different SPA frameworks, the actual pages are coded using vanilla JavaScript.

Key takeaways:

* how to handle the necessary request parameters
* how to contact the backend of IdentityServer to implement the various workflows (login, logout, etc.)
* how to implement a backend to support the frontend pages

[link to source code]({{< param samples_base >}}/UserInteraction/SpaLoginUi)

### Adding other protocol types to dynamic providers

The [dynamic providers]({{< ref "/ui/login/dynamicproviders">}}) feature allows for loading OpenID Connect identity provider configuration dynamically from a store. This sample shows how to extend the dynamic providers feature to support additional protocol types, and specifically WS-Federation.

Key takeaways:

* how to define a custom identity provider model
* how to map from the custom identity provider model to the protocol options
* how to register the custom protocol type with IdentityServer
* how to register the custom protocol type with IdentityServer
* how to use the existing provider store to persist custom provider model data

[link to source code]({{< param samples_base >}}/UserInteraction/WsFederationDynamicProviders)

### Client Initiated Backchannel Login (CIBA)
This sample shows how a client can make [CIBA]({{< ref "/ui/ciba">}}) login requests using Duende IdentityServer.
To run the sample, the IdentityServer and API hosts should be started first.
Next run the ConsoleCibaClient which will initiate the backchannel login request.
The URL the user would receive to login and approve the request is being written out to the IdentityServer log (visible in the console window).
Follow that URL, login as "alice", and then approve the login request to allow the client to receive the results.

[link to source code]({{< param samples_base >}}/UserInteraction/Ciba)

### Windows Authentication with IIS Hosting
This sample shows how to use Windows Authentication when hosting your IdentityServer behind IIS (or IIS Express).
The salient piece to understand is a new *LoginWithWindows* action method in the *AccountController* from the quickstarts.
Windows authentication is triggered, and once the result is determined the main authentication session cookie is created based on the *WindowsIdentity* results.
Also, note there is some configuration in *Startup* with a call to *Configure\<IISOptions>* (mainly to set *AutomaticAuthentication* to *false*).

[link to source code]({{< param samples_base >}}/UserInteraction/WindowsAuthentication/IIS)
