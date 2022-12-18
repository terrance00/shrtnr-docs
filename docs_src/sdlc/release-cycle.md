# Release Cycle

New versions will be released a sprint behind - allowing them to go through a QA cycle.

The new version will be decided based on the semantic versioning principle:

`X.Y.Z`

- For a new feature (non-breaking), the `Y` number will be incremented.
- For bugfixes only, the `Z` number will be incremented.
- The _major_ version `X` will only be updated upon making a breaking change.

## Rollbacks

> To design a good microservices system, one needs to strive to make all the services stateless.

With the above principle in mind, rolling back service versions should be as simple as updating the **k8s manifest** file.

## Backups

Services that aren't stateless by definition. Like databases, queues and caching services should be backed up before doing any releases.
