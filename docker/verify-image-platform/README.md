# Verify Docker Image Platform GitHub Action

Verifies that a Docker image is available for a certain OS and architecture combination by attempting to pull it.

## Example
To use the GitHub Action, you'll need to add it as a step in your [workflow file](https://help.github.com/en/actions/automating-your-workflow-with-github-actions).

```yaml
on: push

jobs:
  publish:
    runs-on: ubuntu-latest
    steps:
      - name: Ensure linux/arm64 Docker image is published
        uses: steadybit/github-actions/docker/verify-image-platform@v1
        with:
          image: docker.steadybit.io/steadybit/agent:latest
          os: linux
          architecture: arm64
      - name: Ensure linux/amd64 Docker image is published
        uses: steadybit/github-actions/docker/verify-image-platform@v1
        with:
          image: docker.steadybit.io/steadybit/agent:latest
          os: linux
          architecture: amd64
```

## Inputs

| Name           | Type   | Required? | Default | Description                                                                            |
|----------------|--------|-----------|---------|----------------------------------------------------------------------------------------|
| `image`        | string | yes       |         | The Docker image reference to verify, e.g., docker.steadybit.io/steadybit/agent:latest |
| `os`           | string | yes       |         | The expected operating system, e.g., linux                                             |
| `architecture` | string | yes       |         | The expected system architecture, e.g., arm64                                          |

## Outputs

None for now.
