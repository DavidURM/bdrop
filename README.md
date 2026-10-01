# bdrop
This program is an offline ["airdrop"](https://en.wikipedia.org/wiki/AirDrop) or [Microsoft Link](https://en.wikipedia.org/wiki/Phone_Link) implementation using bluetooth. It is made in the inspiration of [LocalSend](https://localsend.org/) to optimize workflow and allow a one-way filesharing session for sending notes to your device. A simple command line program that uses xclip and gracefully initiates a file drop session with whatever is currently in your clipboard for your device of choice. Written in bash and runnable in your command line.

## Why?

- Are you tired of having O(denied) search time for LocalSend or any other HTTP file-sharing implementation on eduRoam (or any network whith strict WI-FI AP isolation) ?

- Do you want to just simply send a screenshot to your tablet without having to worry if your screenshot ends up in an LLM dataset?

- Do you feel left out that you don't have airdrop features on your Linux machine?

Then look no further, bdrop looks to solve all of that!

# Features
- **Offline Transfer:** Ignores local Wi-Fi restrictions entirely by using standard Bluetooth Object Exchange (OBEX).
- **Smart Clipboard Detection:** Automatically detects whether your clipboard contains text or an image (screenshot) and formats the file accordingly.
- **Auto-Detection:** Automatically scans for and identifies already-paired devices during initial setup.
- **Cross-Compatible:** Supports both Wayland (`wl-clipboard`) and X11 (`xclip`) desktop environments.

- **No offset telemtry:** No third-party servers, no tracking, no hidden background states, just your hardware doing what it is meant to do.

## Prerequisites
Your Linux system must have the following packages installed:
* `bluez` (Provides `bluetoothctl`)
* `gnome-bluetooth-sendto` (Native GNOME Bluetooth transfer UI)
* `wl-clipboard` (If using Wayland) OR `xclip` (If using X11)

## Installation Debian / Ubuntu

- Install the required dependencies:

```sudo apt install bluez gnome-bluetooth-sendto wl-clipboard xclip```


- Download bdrop to /usr/local/bin:

```sudo wget -O /usr/local/bin/bdrop https://github.com/DavidURM/bdrop/-/raw/main/bdrop```

(Or any other directory)

- Make it executable:

```sudo chmod +x /usr/local/bin/bdrop```

(Or any other directory)

- Usage

- Run in your terminal:

```bdrop```


On the first run, bdrop will guide you through the initial setup.

- Initial setup

An initial Bluetooth pairing is required so bdrop can determine the receiver's Bluetooth address.

- You can either:

Pair the devices using your system's Bluetooth settings and let bdrop detect the receiver.

Manually enter the Bluetooth address of the receiving device when prompted.

Once the setup is complete, press Enter and you're ready to use bdrop.

Change the Bluetooth device

- If you need to change the receiver's Bluetooth address later, use the config command:

```bdrop config```


Follow the prompts to update the configured Bluetooth device.

# Roadmap Planned for a future release:



## Pair and store multiple Bluetooth devices.

Choose the destination device when running bdrop.

## Enable VPN filesharing.

Add a VPN feature for sending to a "home" device.

## Key-board bindability

Enable to directly bind to your screenshot shortcut on your machine

## MacOs - Other devices

Enable bypassing the airdrop completely if you choose a non-Mac device. Currently tested for Linux -> Device