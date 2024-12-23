# `@centos-workstation/bootc-image-builder-action`

Build bootc images into disk images or ISOs.

Currently only ISOs are supported, but contributions are welcome.

## Usage

### Inputs

```yaml
- uses: centos-workstation
  with:
    # Configuration file for the image builder.
    # Required.
    config-file:

    # The expected artifact type
    # Optional. Default is 'iso'
    type:

    # Image (registry with tag) used in the artifact.
    # Required.
    image:

    # The upstream builder image.
    # Optional. Default is 'quay.io/centos-bootc/bootc-image-builder:latest'
    bootc-image-builder-image:
```

### Outputs

| Name | Description | Example |
| - | - | - |
| `output-directory` | Directory containing all output artifacts | `./outputs/buildiso` |
| `output-path` | Path to the build file | `./outputs/buildiso/install.iso` |
| `checksum-path` | Path to the checksum file | `./outputs/buildiso/CHECKSUM` |
| `checksum` | Checksum of the build file | `sha256:...` |
