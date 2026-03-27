# Viseron Home Assistant Add-on

Viseron is a self-hosted, local only NVR and AI Computer Vision software.
With features such as object detection, motion detection, face recognition and more, it provides a powerful solution for your surveillance needs.

## Installation

1. Add this repository to your Home Assistant add-on store.
2. Install the Viseron add-on.
3. Start the add-on.
4. Open the Web UI to access Viseron.

## Configuration

Viseron configuration is managed through its own `config.yaml` file, **not** through Home Assistant add-on options.

On first startup, Viseron will automatically generate a default `config.yaml` in the add-on config directory. You can then edit this file to configure your cameras, detectors, and other settings.

For detailed configuration options, see the [Viseron documentation](https://viseron.netlify.app/docs/documentation/configuration).

### Database

Viseron uses PostgreSQL for its database, which runs internally within the container. The database is stored in the add-on config directory.

## Hardware Acceleration

Viseron supports various hardware acceleration options for video decoding/encoding and AI inference, but options are limited when running in a Home Assistant add-on environment.

### Intel VAAPI (Quick Sync)

Intel GPUs are automatically detected. Make sure the `/dev/dri` device is accessible (enabled by default).

### Google Coral TPU

USB Coral TPU devices are automatically detected when connected. The add-on has USB access enabled by default.

For PCIe Coral devices, ensure `/dev/apex_0` is accessible.

### Hailo AI Accelerators

Hailo devices (`/dev/hailo0`) are included in the device list by default.

## Logs

View the add-on logs through the Home Assistant UI or access the log file directly in the add-on config directory.

## Support

- [Viseron Documentation](https://viseron.netlify.app/)
- [GitHub Issues](https://github.com/roflcoopter/viseron/issues)
- [GitHub Discussions](https://github.com/roflcoopter/viseron/discussions)
