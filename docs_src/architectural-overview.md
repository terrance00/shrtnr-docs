# Architectural Overview

### Services

- [shrtnr-api](services/shrtnr-api.md) - _.Net application_
- [shrtnr-oidc](services/shrtnr-oidc.md) - _.Net application_
- [shrtnr-analytics](services/shrtnr-analytics.md) - _.Net application_
- [shrtnr-ui](services/shrtnr-ui.md) - _React application_
- [shrtnr-redirector](services/shrtnr-redirector.md) - _.Net application_

### System

- In short, the entire system will be deployed as a **Kubernetes** cluster (AKS), with load balancers for the public facing services.
- Our applications and services will be packaged as **Docker** images.
- In addition to the k8s system, we will have two data-stores.
    - [**MongoDB**](data-stores/shrtnr-redirector-store.md) backing the redirector as a horizontally scaleable document store.
    - [**Postgres**](data-stores/shrtnr-db.md) backing the API and OIDC service as a relational store.
- Additional infrastructure includes a __RabbitMQ__ instance for queueing up analytics data to be consumed by the analytics service.

### Diagram

``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```


### Flows

#### User shortening a URL:

``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```

#### User following a shortened link:

``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```