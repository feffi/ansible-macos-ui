# ansible-macos-ui
Ansible role to manage UI settings in macOS.

[![Build Status](https://img.shields.io/travis/feffi/ansible-macos-ui.svg)](https://travis-ci.org/feffi/ansible-macos-ui) [![Github All Releases](https://img.shields.io/github/downloads/feffi/ansible-macos-ui/total.svg)](https://github.com/feffi/ansible-macos-ui) [![GitHub forks](https://img.shields.io/github/forks/feffi/ansible-macos-ui.svg?style=social&label=Fork)](https://github.com/feffi/ansible-macos-ui) [![GitHub stars](https://img.shields.io/github/stars/feffi/ansible-macos-ui.svg?style=social&label=Star)](https://github.com/feffi/ansible-macos-ui) [![GitHub watchers](https://img.shields.io/github/watchers/feffi/ansible-macos-ui.svg?style=social&label=Watch)](https://github.com/feffi/ansible-macos-ui) [![Twitter Follow](https://img.shields.io/twitter/follow/feffi1.svg?style=social&label=Follow)](https://twitter.com/feffi1) [![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/feffi/ansible-macos-ui/blob/master/LICENSE)

## Requirements
- Ansible 2.3

### ansible.cfg
```
hash_behaviour = merge
```

## Install
Just add the role to your ``requirements.yml`` file:
```yaml
- src: https://github.com/feffi/ansible-macos-ui.git
  name: feffi.macos-ui
```

## Role Variables
All role based variables are listed below, along with default values:

```yaml
macos_ui:
  # Enable Dashboard dev mode (allows keeping widgets on the desktop)
  dashboard_devmode: true

  # Enable Dashboard
  dashboard_enable: false

  # Set Help Viewer windows to non-floating mode
  help_floating: true

  # Quit Printer App After Print Jobs Complete
  quit_printer: true

  # Set shadow in screenshots
  screenshots_shadow: false

  # Set screenshots save path
  screenshots_path: "~/Desktop/Screenshots"

  # Set screenshots save format, options: png, bmp, gif, jpg, pdf, tiff
  screenshots_format: "png"

  # Ask for password on screensaver
  screensaver_password: true

  # Ask for password on screensaver delay in seconds
  screensaver_password_delay: 0

  # Use scroll gesture with the Ctrl (^) modifier key to zoom
  zoom: "262144"

  # Follow the keyboard focus while zoomed in
  zoom_follow: true

  # Set Menu bar transparency
  menubar_transparency: true

  # Enable subpixel font rendering on non-Apple LCDs
  subpixel: 2

  # Set highlight color to green
  highlight: "0.764700 0.976500 0.568600"

  # Enable full keyboard access for all controls (e.g. enable Tab in modal dialogs)
  keyboard_mode: 3

  # Double-click a window's title bar to minimize
  window_dbclk: true

  # Use smooth scrolling
  smooth_scroll: true

  # Show scrollbars only when scrolling
  scrollbar_mode: "WhenScrolling"

  # Natural (Lion-style) scrolling
  scroll_natural: true

  # Set opening and closing windows and popovers
  opening_animation: false
```

## Dependencies
None.

## Example Playbook

```yaml
    - hosts: all
      vars:
      macos_ui:
        hostinfo: "HostName"
        hidpi: true
        dashboard_devmode: true
        dashboard_enable: false
        help_floating: true
        quit_printer: true
        screenshots_shadow: false
        screenshots_path: "~/Desktop/Screenshots"
        screenshots_format: "png"
        screensaver_password: true
        screensaver_password_delay: 0
        zoom: "262144"
        zoom_follow: true
        menubar_transparency: true
        subpixel: 2
        highlight: "0.764700 0.976500 0.568600"
        keyboard_mode: 3
        window_dbclk: true
        smooth_scroll: true
        scrollbar_mode: "WhenScrolling"
        scroll_natural: true
        opening_animation: false
      roles:
        - { role: feffi.macos-ui }
```
Or with local parameters:

```yaml
    - hosts: all
      roles:
        - { role: feffi.macos-ui,
            macos_ui: {
              hostinfo: "HostName",
              hidpi: true,
              dashboard_devmode: true,
              dashboard_enable: false,
              help_floating: true,
              quit_printer: true,
              screenshots_shadow: false,
              screenshots_path: "~/Desktop/Screenshots",
              screenshots_format: "png",
              screensaver_password: true,
              screensaver_password_delay: 0,
              zoom: "262144",
              zoom_follow: true,
              menubar_transparency: true,
              subpixel: 2,
              highlight: "0.764700 0.976500 0.568600",
              keyboard_mode: 3,
              window_dbclk: true,
              smooth_scroll: true,
              scrollbar_mode: "WhenScrolling",
              scroll_natural: true,
              opening_animation: false
            }
          }
```
