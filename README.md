[![Build Status](https://travis-ci.org/smokris/GetWindowID.svg?branch=master)](https://travis-ci.org/smokris/GetWindowID)

GetWindowID
===========

macOS command line utility to retrieve the CGWindowID of the specified
window (useful for screencapture).


## Installation

Via Homebrew:

```bash
    brew install gsbabil/getwindowid/getwindowid
```


## Usage

```bash
    ./GetWindowID <application-bundle-name> <window-title>
```

For example, to get the ID of the iOS/tvOS/watchOS Simulator:

```bash
    ./GetWindowID Simulator 'iPhone X - iOS 11.0'
```

…and to capture a screenshot of it:

```bash
    screencapture -l$(./GetWindowID Simulator 'iPhone X - iOS 11.0') simulator.png
```

To get the ID of a window without a title, pass an empty string as the title:

```bash
    ./GetWindowID GLFW ''
```

To list all of an app's windows, pass `--list` as the title:

```bash
    ./GetWindowID Simulator --list
```

## Notes

* `Terminal.app` and `sshd-keygen-wrapper` must be added and enabled in
  the following system settings. Otherwise, the "title" information of
  the apps will appear as "(null)" due to MacOS's privacy and security
  features.

    ```
      MacOS Settings.app 
        > Privacy & Security 
        > Accessibility 
        > Allow the applications below to control your computer.
    ```
