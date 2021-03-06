# BlackHole Virtual Audio Driver v0.2

[![Platform:macOS](https://img.shields.io/badge/platform-macOS-lightgrey)
![GitHub](https://img.shields.io/github/v/release/ExistentialAudio/BlackHole)
![GitHub All Releases](https://img.shields.io/github/downloads/existentialaudio/blackhole/total)](https://github.com/ExistentialAudio/BlackHole/releases)
[![GitHub](https://img.shields.io/github/license/ExistentialAudio/BlackHole)](LICENSE)
[![Build Status](https://travis-ci.com/ExistentialAudio/BlackHole.svg?branch=master)](https://travis-ci.com/ExistentialAudio/BlackHole)

[![Twitter Follow](https://img.shields.io/twitter/follow/ExistentialAI?style=social)](https://twitter.com/ExistentialAI)

## Description
BlackHole is a modern MacOS virtual audio driver that allows applications to pass audio to other applications with zero additional latency.

- [Features](#features)
- [Easy Installation Instructions](#easy-installation-instructions)
- [Usage Examples]()
- [Advanced Installation Instructions](#advanced-installation-instructions)
- [Advanced Customization](#advanced-customization)
- [Feature Requests](#feature-requests)
- [FAQ](#faq)
- [Wiki](https://github.com/ExistentialAudio/BlackHole/wiki)

## Features
- Supports 16 audio channels.
- Customizable to 256+ channels if you think your computer can handle it.
- Supports 44.1kHz, 48kHz, 88.2kHz, 96kHz, 176.4kHz, and 192kHz sample rates.
- No additional driver latency. 
- Works on macOS 10.10+ including macOS 10.15 Catalina

![Image of BlackHole Audio Driver](Images/BlackHole.png)

## Easy Installation Instructions
1. Download [BlackHole.vx.x.x.pkg](https://github.com/ExistentialAudio/BlackHole/releases/)
2. Close all running audio applications
3. Right-click on package and select open
4. Open and install package
5. Restart Computer (Catalina Only)

BlackHole is also available using `brew cask install blackhole`

Visit the [Wiki](https://github.com/ExistentialAudio/BlackHole/wiki) for application specific setup.

## Usage Examples
### Record System Audio
1. Open Audio MIDI Setup
2. Right-click on "BlackHole" and select "Use This Device For Sound Output"
3. Open DAW and set input device to "BlackHole" 
4. Set track to input from channel 1-2
5. Play audio from another application and monitor or record in your DAW.

### Route Audio Between Applications
1. Set output driver to "BlackHole" in sending application
2. Output audio to any channel
3. Open receiving application and set input device to "BlackHole" 
4. Input audio from the corresponding output channels

## Advanced Installation Instructions
1. Build driver in Xcode
2. Copy BlackHole.driver to `/Library⁩/Audio⁩/Plug-Ins⁩/HAL`
3. Restart CoreAudio with terminal command `sudo killall coreaudiod`

## Advanced Customization
1. In "BlackHole.h" change `NUMBER_OF_CHANNELS` to the desired number of channels.
2. Follow [Advanced Installation Instructions](#advanced-installation-instructions)

## Uninstallation Instructions
1. Delete BlackHole.driver from `/Library⁩/Audio⁩/Plug-Ins⁩/HAL`
2. Restart computer or restart CoreAudio with terminal command `sudo killall coreaudiod`

## Feature Requests

If you are interested in any of the following features please leave a comment in the linked issue. If you want any features not listed please create a new issue.

- [Sync Clock with other Audio Devices](https://github.com/ExistentialAudio/BlackHole/issues/27)
- [Output Blackhole to other Audio Device](https://github.com/ExistentialAudio/BlackHole/issues/40)
- [Add Support for AU Plug-ins](https://github.com/ExistentialAudio/BlackHole/issues/18)
- [Inter-channel routing](https://github.com/ExistentialAudio/BlackHole/issues/13)
- [Record Directly to File](https://github.com/ExistentialAudio/BlackHole/issues/8)
- [Configuration Options Menu](https://github.com/ExistentialAudio/BlackHole/issues/7)

## FAQ

### Why isn't BlackHole showing up in the Applications folder?
BlackHole is an audio interface driver. It only shows up in `Audio MIDI Setup`, `Sound Preferences`, or other audio applications.

### How can I listen to the audio and use BlackHole at the same time?
[Setup a Multi-Output Device](https://github.com/ExistentialAudio/BlackHole/wiki/Multi-Output-Device)

### How can I change the volume of a Multi-Output device?
Unfortunately macOS does not support changing the volume of a Multi-Output device but you can set the volume of individual devices in Audio MIDI Setup. 

### How can I use BlackHole with Audacity in Catalina?
Audacity is not compatible with Catalina. But there might be a [work around](https://www.audacityteam.org/macos-10-15-catalina-is-not-yet-supported-by-audacity/).

### Why is nothing is playing through BlackHole? 
Check `System Preferences` -> `Security & Privacy` -> `Privacy` -> `Microphone` to make sure your DAW has microphone access. 

Check that the volume is all the way up on BlackHole input and output in ``Audio Midi Setup``.

### Can I integrate BlackHole into my app?
BlackHole is licensed under GPL-3.0. You can use BlackHole as long as your app is also licensed as GPL-3.0. For all other applications contact me directly at devinroth@existential.audio.

### You are awesome. Where can I donate?
[Support us on Patreon](https://www.patreon.com/existentialaudio)

Bitcoin:  1DxkhWHfRUBezMNbRM3rDKLbxEi1GVZRXz

Litecoin: LchR249L8aXnDEDToLpPVSJotuvV381Yka
