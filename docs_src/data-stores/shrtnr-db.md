# Shrtnr DB

This will be the main _relational_ database.

This database will support the following services:

- [OIDC](../services/shrtnr-oidc.md)
    - This is the identity service and will keep track of user identity.
    - this service will use __OpenIddict__ as the identity library. Check out the docs [here](https://documentation.openiddict.com/guides/index.html).
- [Analytics](../services/shrtnr-analytics.md)
    - This service keeps track of analytical data surrounding the redirect service.

![postgres](../assets/postgresql.png)