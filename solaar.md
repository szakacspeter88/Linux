Installing Solaar on Arch Linux is straightforward because it is available 
in the official repositories. However, you'll need a couple of extra steps to
ensure it has the correct permissions to talk to your Logitech receiver without
needing sudo every time.

1. Install the Package

Open your terminal and run the following command to install Solaar from the official extra repository:
Bash

```
sudo pacman -S solaar
```

2. Configure Permissions (Udev Rules)

By default, your user might not have permission to access the Logitech receiver device files. The Solaar package includes udev rules, but you need to make sure they are active.

Reload udev rules:
Bash
```
sudo udevadm control --reload-rules
```
Apply permissions: Unplug your Logitech receiver and plug it back in. This triggers the new rules so your user account can access the device.

[!TIP] GNOME Users: If you want the Solaar icon to appear in your system tray, you should also install the optional dependency libayatana-appindicator.
Bash
```
sudo pacman -S libayatana-appindicator3
```

3. Usage

You can start the GUI from your application launcher or by running:
Bash

```
solaar
```

If you prefer to keep it hidden in the tray on startup, use:
Bash

```
solaar --window=hide
```

Troubleshooting

Device not found? Ensure your user is part of the plugdev group 
if your system uses it, though modern Arch setups usually handle
this via uaccess in the udev rules automatically.
Permissions still failing? A full reboot is often the cleanest way
to ensure all group memberships and udev rules are properly initialized.
