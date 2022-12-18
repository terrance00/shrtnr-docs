# Automation

## Service containerization

Every service will have a docker file and upon successfull PR will be compiled and packaged into a docker container. The container registry of choice should be hosted on the relevant cloud server - _Azure container registry (ACR)_ for our purposes.

These will be versioned according to the versioning strategy below

## Deployments

A **k8s** manifest will exist within a repo, for _development_ and _master_ branches. Deployments will occur automatically from these manifests.

In addition all logic for deploying and maintaining load balancers and external data services will exist as deployment scripts on this repo in the form of _Azure pipelines_.

## Versioning

**Semantic versioning** wil be used. That is to say `x.y.z` where `x` is the major version (used for breaking changes), `y` is the feature version (used for new features) and `z` is the bug version, used for any hotfix or bug.

For the _development environment_, all merged PR's will be built and deployed as the _next version_ (AKA `x.y.x+1-{build-number}`) with the build number appended. With the build number appened all deployed versions will be easy to track back to a commit hash.
