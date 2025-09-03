# Tuya Outlet CLI

A simple Python CLI to control a Tuya-compatible 3-way smart power strip **over your local network** without using the Tuya cloud (except once during setup). Basically just a simple wrapper around the awesome [tinytuya](https://github.com/jasonacox/tinytuya) project.

## Features
- Turn each plug **on/off** individually
- Show status including plug states and energy data (voltage, current, power)
- Simple setup command for device configuration
- Robust configuration management with timeout and retry options

## Setup

1. Clone this repo:
```bash
git clone https://github.com/yourname/tuya-powerstrip-cli.git
cd tuya-powerstrip-cli
```

2. Install dependencies:
```bash
poetry install
```

3. Configure your device credentials:
```bash
poetry run tuya-strip setup
```

The setup command will prompt you to enter your device details:
- Device ID
- Device IP address
- Local Key
- Protocol Version (default: 3.3)

Configuration is saved to your home directory (`~/.tuya-strip`) and will work from any directory.

## Usage
```bash
poetry run tuya-strip status          # Show current state and energy data
poetry run tuya-strip on 1            # Turn on plug 1
poetry run tuya-strip off 3           # Turn off plug 3
poetry run tuya-strip --timeout 5 status  # Use custom timeout
poetry run tuya-strip --retries 5 on 2    # Use custom retry count
```

## Example Output
```yaml
Loading config from: C:\Users\username\.tuya-strip
Switches: {'1': True, '2': False, '3': True}
Energy: {'voltage_V': 229, 'current_mA': 120, 'power_W': 24}
```
