*Note: this repo is out of date. The updated repo is [here](https://github.com/scottpham/sensorkit)*
# PiBakery for Arizona Newshacking

This repo contains a `.xml` file intended to be imported by the PiBakery program. It bootstraps a fresh Raspbian install with software updates and ensures that VNC is enabled with a unique hostname. That way you can simply SSH or VNC into "PIHOSTNAME.local" without having to know the IP address of the Pi.

### What this recipe does:
- Sets up wifi
- Changes the hostname
- Enables the I2C and SPI pins
- Enables login over the GPIO serial (just in case)
- Downloads a bootstrap script from github gists and runs it

### What the bootstrap script does:
- Runs a full update/upgrade of Raspbian packages
- Enables VNC login at boot
- Changes the Pi keyboard to American-style
- Changes the locale/timezone to Phoenix
- Installs vim(just for fun) and iPython (important for teaching)
- Installs various python extensions, which are dependencies for sensors
- Installs the Adafruit_DHT library for the DHT_22 sensor

### How to use:

1. "Import" the `.xml` file with PiBakery
2. Change the `hostname` block to a unique hostname.
3. Change the `wifi` block(s) to your wifi information
4. Make sure your pi has access to wifi and is plugged into a monitor and keyboard
5. Put the SD card in the Pi and turn it on
6. Wait about 1 hour

When the Pi starts up for the first time after the bootstrap it won't have VNC access right away. This has something to do with the OS update and will happen only once. Reboot the pi or shut it down, and the next time it boots it will be ready to go. It helps to have the Pi plugged into a monitor and keyboard for this, but afterwards you can use SSH/VNC exclusively if you like.


