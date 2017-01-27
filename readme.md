## PiBakery for Arizona Newshacking

This repo contains a `.xml` file intended to be imported by the PiBakery program. It bootstraps a fresh Raspbian install with software updates and ensures that VNC is enabled with a unique hostname. That way you can simply VNC into "PIHOSTNAME.local".

### What this recipe does:
- Sets up wifi
- Changes the hostname of the Pi (for easy ssh login)
- Enables the I2C and SPI pins
- Enables login over the GPIO serial (just in case)
- Downloads a bootstrap script from github gists and runs it

### What the bootstrap script does:
- Does a full update/upgrade of Raspbian packages
- Enables VNC login at boot
- Changes the Pi keyboard to American-style
- Changes the locale/timezone to Phoenix
- Installs vim and iPython
- Installs various python extensions, which are dependencies
- Installs the Adafruit_DHT library for the DHT_22 sensor

### How to use:

1. "Import" the `.xml` file with PiBakery and then write to an SD card
2. Change the `hostname` block to a unique hostname. This ensures we can VNC or SSH into the desktop without knowing the IP address of the Pi.
3. Change the `wifi` block(s) to your wifi information
4. Make sure your pi has access to wifi and is plugged into a monitor and keyboard
5. Put the SD card in the Pi and turn it on
6. Wait about 1 hour

When the Pi first starts up, it won't have VNC access right away and its hostname won't be set. Reboot the pi or shut it down, and the next time it boots it will be ready to go.
