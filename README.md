# SirrAT

SirrAT is a lightweight, terminal-based modem management tool built around standard AT commands.
It is designed for direct interaction with USB modems on Linux systems, focusing on simplicity, transparency, and control.

The tool is written entirely in Bash and uses atinout to communicate with modem serial interfaces.

---

## Features

* Automatic detection of USB modem ports (ttyUSB devices)
* Interactive menu-based interface
* Modem information queries:

  * IMEI
  * IMSI
  * Signal strength (CSQ)
* Real-time signal strength monitor with visual bar
* BTS and operator information lookup
* IMEI change support (advanced and modem-dependent)
* Modem reboot via AT commands
* Polkit integration for secure privilege escalation

---

## Requirements

* Linux system
* USB modem with AT command support
* Root privileges (handled via polkit and pkexec)
* Required dependencies:

  * atinout
  * policykit-1
  * pkexec

---

## Installation

Install the package using dpkg:

```
sudo dpkg -i sirrat_VERSION_arm64.deb
```

If dependencies are missing, fix them with:

```
sudo apt -f install
```

After installation, SirrAT can be launched:

* From the desktop application menu
* From the terminal using pkexec

---

## Usage

1. Launch SirrAT with elevated privileges
2. Select the detected modem port
3. Choose an action from the interactive menu

Available actions include:

* Show IMEI
* Show IMSI
* Show signal strength
* Real-time signal monitoring
* Display BTS and operator information
* Change IMEI (advanced)
* Reboot modem

---

## IMEI Change Warning

Changing the IMEI is hardware-specific and may not work on all modems.
In some countries, modifying the IMEI is illegal.

Use this feature only if you understand the legal and technical implications.

---

## Security Model

SirrAT requires root access to communicate with modem devices.
When launched from the desktop environment, authentication is handled via polkit instead of sudo, improving security and usability.

---

## Project Philosophy

* Minimal dependencies
* No background services
* Transparent AT command usage
* Simple and auditable Bash code
* Designed for power users and embedded systems

---

## Author

Commander.Z3R0

---
