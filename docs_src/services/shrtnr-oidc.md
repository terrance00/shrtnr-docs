# Shrtnr OIDC

This server will employ the standardized [_OIDC_](https://openid.net/connect/) protocol for managing user identity and security.

## Proposed Tech

- [.Net](https://learn.microsoft.com/en-us/dotnet/)

To implement OIDC, we can use the following system: [openiddict](https://documentation.openiddict.com/index.html).

This system will be backed by the [shrtnr-db](../data-stores/shrtnr-db.md) data-store - running _postgres_.

## Why OIDC

_OIDC_ specifies industry standards and best practices for managing security and identity.

_Openiddict_, is certified by the OIDC foundation and is completely free and open source.