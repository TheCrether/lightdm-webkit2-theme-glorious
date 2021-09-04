# glorious - a lightdm webkit2 theme

[![maintained](https://img.shields.io/maintenance/yes/2021?label=maintained&style=flat-square)](https://github.com/TheCrether/lightdm-webkit2-theme-glorious/tree/master) [![contributions](https://img.shields.io/badge/contribution-welcome-brightgreen&?style=flat-square)](https://github.com/TheCrether/lightdm-webkit2-theme-glorious/tree/master)

A sleek, modern, and glorified lightdm webkit2 theme

## [Live Demo](https://thecrether.github.io/lightdm-webkit2-theme-glorious)

### Demo password: `toor`

<p align='center'><img alt='glorious' src='glorious.gif'/><br/><i>glorious - a lightdm webkit 2 theme</i></p>

### Dependencies

This fork of the theme is made to be compatible with the latest version that is available in the [AUR](https://archlinux.org/packages/community/x86_64/lightdm-webkit2-greeter/). Please make sure you don't have an ancient version of these.

+ lightdm
+ lightdm-webkit2-greeter

### Installation

0. If you're using `systemd`, make sure that `lightdm.service` or `lightdm-plymouth.service` is enabled and running. There's a bunch of guides on the internet. [Archwiki](https://wiki.archlinux.org/index.php/LightDM) is recommended.

1. Install it. You can get the theme by cloning this repo or by installing it.

    - Clone the repo

        1. Download and extract the latest stable release from [here](https://github.com/Thecrether/lightdm-webkit2-theme-glorious/releases).
        2. Copy it to the lightdm-webkit theme folder:

        ```sh
        cp -r lightdm-webkit2-theme-glorious /usr/share/lightdm-webkit/themes/glorious-crether
        ```

2. Set lightdm greeter session to webkit0.

     ```sh
     # Set default lightdm greeter to lightdm-webkit2-greeter
     sudo sed -i 's/^\(#?greeter\)-session\s*=\s*\(.*\)/greeter-session = lightdm-webkit2-greeter #\1/ #\2g' /etc/lightdm/lightdm.conf
     ```

3. Set it as the lightdm webkit2 theme then enable `debug_mode` by setting it to `true`. Why do we need to enable `debug_mode`? Sometimes you will be greeted by an error. And this error is due to a race condition where the theme is trying to access the `lightdm` object even though it doesn't exist *yet*. Debug mode will allow you to `right-click` and `reload` the greeter just like a webpage.

     ```sh
     # Set default lightdm-webkit2-greeter theme to Glorious
     sudo sed -i 's/^webkit_theme\s*=\s*\(.*\)/webkit_theme = glorious-crether #\1/g' /etc/lightdm/lightdm-webkit2-greeter.conf
     sudo sed -i 's/^debug_mode\s*=\s*\(.*\)/debug_mode = true #\1/g' /etc/lightdm/lightdm-webkit2-greeter.conf
     ```

### Uninstall

1. Follow the [installation instruction](#installation) in reverse order.

### Features

+ Multi-user support
+ Customization and Settings
+ Keyboard navigation
+ Remappable keybindings
+ Swipe gestures
+ Vanilla Javascript!

### Swipe gestures

Why do we have this? Linux can be installed on almost anything. Yes, even on a potato. So it exists to save myself some time if someone (including myself) decided to use this theme on a touch screen device (like touch screen potato? Who knows).

+ Swiping up on the greeter screen will close it.
+ Swiping down on the login screen will open the greeter screen.
+ Swiping left will open the dashboard.
+ Swiping right will close the dashboard.

### Keybinds

The default modifier is <kbd>Alt</kbd>. You can change it in the settings.

+ <kbd>Modifier + s</kbd> opens the dashboard.
+ <kbd>Modifier + e</kbd> opens the session selection.
+ <kbd>Modifier + x</kbd> opens the power selection.
+ <kbd>Modifier + y</kbd> opens the account selection.
+ <kbd>Escape</kbd> to close or go back.

### Customization and Settings

+ Color customization supports `#RGB`, `#RRGGBB`, and `#RRGGBBAA`.
+ Blur strength settings only allows an integer with `px` suffix.
+ Animation speed supports `s` and `ms`.
+ Background image selection. Supports randomness.

### Changing clock mode

There are two clock modes available - `24-hour` and `12-hour`. Switch between clock modes by just clicking on the clock. Simple.

### Notes

+ Add more background images by putting your wallpapers/images in `/usr/share/backgrounds/`.
+ Non-image and directory inside `/usr/share/backgrounds/` will cause an error! You will likely encounter this if you installed a package (for example `archlinux-wallpaper` that includes `AUTHORS` file).
+ Set your profile image in system settings or by using `mugshot`.
+ Missing DE/WM logo? Submit a [pull request](https://github.com/TheCrether/lightdm-webkit2-theme-glorious/pulls)!
+ Translations are not yet supported. PR's are welcome!

### Credits

<span>Background image by <a href="https://unsplash.com/@korpa?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Jr Korpa</a> on <a href="https://unsplash.com/s/photos/cherry-blossoms-purple?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a></span>
