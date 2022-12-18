# Analytics

The analytics service will provide insights and value to customers.

## Proposed tech

- This service will simply need to subscribe to a queue, ingest the data and persist it.
- [.Net](https://learn.microsoft.com/en-us/dotnet/), or [NodeJS](https://nodejs.org/en/docs/) will be perfectly suited to this task.

## Data feed

The data for providing valuable insights to users of the system will be fed into a _RabbitMQ_ instance by the [redirector](./shrtnr-redirector.md).

The analytics service will be subsribed to the above queue and ingest the data provided.

Users will be able to access this data through the [UI](./shrtnr-ui.md).
