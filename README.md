# KNAW-HUC Starter Workflows

## build-push
### Description

Build and then push an OCI container image built from a single Dockerfile and push it to a registry.

All variables have a default value set, images will be pushed to the _packages_ of the github organization when using these default settings. See the _vaiables_ subsection for the available options.

### Variables
| tab | description | data type | default value |
|---|---|---|---|
| REGISTRY_FQDN | The url of the registry to push the image to | string | ghcr.io |
| REGISTRY_USERNAME | Username for the registry, used to authenticate | string | ${{ github.actor }} |
| REGISTRY_PASSWORD | Password for the registry, used to authenticate | string | ${{ secrets.GITHUB_TOKEN }} |
| IMAGE_NAME | Name for the image, images are tagged `<IMAGE_NAME>/<GIT_TAG>`,<br>with the git tag being the tag that triggers the action | string | repository name |
| IMAGE_FILE | The path for the Dockerfile to use for the build. | string | ./Dockerfile |