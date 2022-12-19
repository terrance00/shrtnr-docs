# Architectural Overview

### Services

- [shrtnr-api](services/shrtnr-api.md)
- [shrtnr-oidc](services/shrtnr-oidc.md)
- [shrtnr-analytics](services/shrtnr-analytics.md)
- [shrtnr-ui](services/shrtnr-ui.md)
- [shrtnr-redirector](services/shrtnr-redirector.md)

### System

- In short, the entire system will be deployed as a **Kubernetes** cluster (AKS), with load balancers for the public facing services.
- Our applications and services will be packaged as **Docker** images.
- In addition to the k8s system, we will have two data-stores.
    - [**MongoDB**](data-stores/shrtnr-redirector-store.md) backing the redirector as a horizontally scalable document store.
    - [**Postgres**](data-stores/shrtnr-db.md) backing the API and OIDC service as a relational store.
- Additional infrastructure includes a **RabbitMQ** instance for queueing up analytics data to be consumed by the analytics service.

### Diagram

```mermaid
flowchart LR
  WEB_APP(Web App) <--> LB_OIDC
  WEB_APP <--> LB_API
  WEB_APP <--> LB_UI
  LB_API((LB: API)) <--> API
  Client_Request(Client Request) <--> LB_REDIRECTOR
  LB_REDIRECTOR((LB: Redirector)) <--> REDIRECTOR
  LB_UI((LB: UI)) <--> UI
  LB_OIDC((LB: OIDC)) <--> OIDC
  subgraph K8S
    UI
    API
    REDIRECTOR
    RABBITMQ --> ANALYTICS
    OIDC <--> API
    REDIRECTOR --> RABBITMQ
  end
  API <--> DB_Mongo[(Redirector Store - Mongo)]
  API <--> DB_Postgres[(Shrtnr DB - Postgres)]
  REDIRECTOR --> DB_Mongo
  ANALYTICS <--> DB_Postgres

```