# `@ublue-os/bootc-image-builder-action`

Build bootc container images into bootable disk images or ISOs.

## Usage

### Inputs

```yaml
- uses: centos-workstation
  with:
    # Configuration file for the image builder.
    # Required.
    config-file:

    # The expected artifact type. Supported values: iso, raw, qcow2, vmdk, vdh, ami, gce.
    # Optional. Default is 'iso'
    type:

    # Image (registry with tag) used in the artifact.
    # Required.
    image:

    # The upstream builder image.
    # Optional. Default is 'quay.io/centos-bootc/bootc-image-builder:latest'
    bootc-image-builder-image:

    # Use librepo for downloading packages for the output image. (can break if you are using an old bib image).
    # Optional. Default is false
    use-librepo:

    # Override the default root filesystem from the source container. Supported values: ext4, xfs, btrfs.
    # NOTE: this option is required only if your image does not define a default (e.g. Fedora). See: https://osbuild.org/docs/bootc
    # Optional. Default is ''
    rootfs:
```

### Outputs

| Name | Description | Example |
| - | - | - |
| `output-directory` | Directory containing all output artifacts | `./outputs/buildiso` |
| `output-path` | Path to the build file | `./outputs/buildiso/install.iso` |
| `checksum-path` | Path to the checksum file | `./outputs/buildiso/CHECKSUM` |
| `checksum` | Checksum of the build file | `sha256:...` |
