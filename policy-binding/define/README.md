# Define Policy Binding GitHub Action

Register a policy binding with Steadybit.

## Example
To use the GitHub Action, you'll need to add it as a step in your [workflow file](https://help.github.com/en/actions/automating-your-workflow-with-github-actions). By default, the only thing you need to do is set the `apiAccessToken` parameter to [Steadybit API access token](https://docs.steadybit.io/integrate/10-api).

```yaml
on: push

jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: steadybit/github-actions/policy-binding/define@v1
        with:
          apiAccessToken: ${{ secrets.STEADYBIT_TOKEN }}
```

## Inputs

|Name              |Type    |Required? |Default                       |Description
|------------------|--------|----------|------------------------------|------------------------------------
|`apiAccessToken`  |string  |yes       |                              |Access Token to be used when accessing the Steadybit API
|`baseURL`         |string  |no        |https://platform.steadybit.io |Base URL of the Steadybit server
|`file`            |string  |no        |.steadybit.yml                |The path to your policy binding file

## Outputs

None for now.
