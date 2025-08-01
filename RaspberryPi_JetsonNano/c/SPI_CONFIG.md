# SPI Configuration Guide

This version of the e-Paper library supports configurable SPI settings to make it easier to work with different hardware platforms.

## Configuration Options

The following Makefile variables can be used to configure SPI settings:

- `SPI_CHANNEL`: SPI channel number (default: 1)
- `GPIO_CHIP`: GPIO chip number (default: 1) 
- `SPI_DEVICE_PATH`: Custom SPI device path (default: auto-generated)

## Platform Examples

### Orange Pi Zero 2W (Default)
```bash
make RPI EPD=epd2in13
# Uses: SPI_CHANNEL=1, GPIO_CHIP=1, SPI_DEVICE_PATH="/dev/spidev1.0"
```

### Standard Raspberry Pi
```bash
make RPI EPD=epd2in13 SPI_CHANNEL=0 GPIO_CHIP=0
# Uses: SPI_CHANNEL=0, GPIO_CHIP=0, SPI_DEVICE_PATH="/dev/spidev0.0"
```

### Custom Configuration
```bash
make RPI EPD=epd2in13 SPI_CHANNEL=0 GPIO_CHIP=1 SPI_DEVICE_PATH="/dev/spidev0.1"
# Uses custom values for all parameters
```

## Supported Libraries

These settings work with all supported GPIO libraries:
- WiringPi (`USE_WIRINGPI_LIB`)
- lgpio (`USE_LGPIO_LIB`) 
- BCM2835 (`USE_BCM2835_LIB`)
- Device library (`USE_DEV_LIB`)

## Migration from Previous Versions

Previous versions had hardcoded SPI settings. To maintain compatibility:

- **Old behavior (channel 0)**: Use `SPI_CHANNEL=0 GPIO_CHIP=0`  
- **Orange Pi Zero 2W (channel 1)**: Use default settings or explicitly set `SPI_CHANNEL=1 GPIO_CHIP=1`

## Notes

- The `SPI_DEVICE_PATH` is automatically generated as `/dev/spidev{CHANNEL}.0` unless explicitly overridden
- GPIO chip selection only affects `lgpio` and `gpiod` libraries
- SPI channel selection affects `wiringPi` and `lgpio` libraries
- BCM2835 library uses its own SPI interface and ignores device path settings
