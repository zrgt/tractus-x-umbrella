# Eclipse Tractus-X Umbrella

This repository is the homebase for all end-to-end test automation efforts at Eclipse Tractus-X.
It contains an umbrella helm chart to deploy a sandbox Catena-X dataspace based on the Tractus-X OSS components, as well as automated tests and workflows to verify the e2e use cases and the compatibility of the OSS components and versions.

## Umbrella Helm Chart

```plantuml
@startuml
Helligkeit -> Dampfdruck
@enduml
```

For details and further information, please refer to the helm chart specific [README](./charts/umbrella/README.md).

## Testing GitHub workflows locally

If you want to try out your new or improved GitHub workflow locally, before pushing, you can try to use
[act](https://github.com/nektos/act). Follow the official [installation instructions](https://github.com/nektos/act#installation)
for your OS/package manager to set it up on your machine.

There is also plenty of documentation on how to use act and simulate events, that would trigger workflow runs on GitHub.
Some workflows might run into issues, when running them locally. This might be caused by missing values for
`${{ github.event }}` references. To fix this, you can provide your own [event](https://github.com/nektos/act#installation)
as `.json` file. There are already examples present in the [/.act](.act) directory.

An local example run via `act` could look like the following: `act -e .act/pr_event.json pull_request`
