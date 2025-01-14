# stryker-dotnet-action
GitHub Action for mutation testing with [Stryker.NET](https://stryker-mutator.io/docs/stryker-net/introduction/) via Docker.

## Usage
This action only accepts a [Stryker Mutator .NET Configuration](https://stryker-mutator.io/docs/stryker-net/configuration) file (`.json` or `.yaml` format).

All Configurations for the Framework must be specified via the Configuration file as currently there is no support for exposing the Framework args.

> [!IMPORTANT]
> The Configuration File must exist at the root level of the Repository.

## GitHub Actions
#### Inputs
`configurationFile` : The name of the Stryker.NET configuration file (must be in the root of the repository).

### Example
```yml
name: Run Stryker.NET

on: push

jobs:
  mutation-testing:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Run Stryker.NET against Repository
        uses: lyndychivs/stryker-dotnet-action@master
        with:
          configurationFile: "stryker-config.json"
```
