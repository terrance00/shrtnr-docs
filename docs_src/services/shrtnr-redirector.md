# Shrtnr Redirector

The redirector service will have a very simple task:

- Receive a request.
- Lookup the target URL in the index optimized _mongodb_ database.
- Queue all the request context data - to be picked up by the [analytics service](./shrtnr-analytics.md).
- Redirect the user.

## Propsed Tech

A very lightweight web application aimed at squeezing as much performance out as possible - The latest version of [.Net](https://learn.microsoft.com/en-us/dotnet/) will be ideal for this use case.
