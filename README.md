# linuxdeploy-plugin-gtk

This is an (as of yet experimental) plugin for linuxdeploy. Its job is to bundle
additional resources for applications that use GTK, and for common dependencies.
Those involve GLib schemas for instance.

## Dependencies

This plugin requires the following dependencies in order to work properly:

-   `file` command
-   `find` command
-   `pkg-config` or `pkgconf` command
-   librsvg2 development files
-   GTK development files

## Usage

```bash
# get linuxdeploy and linuxdeploy-plugin-gtk
-c > wget "https://raw.githubusercontent.com/linuxdeploy/linuxdeploy-plugin-gtk/master/linuxdeploy-plugin-gtk.sh"
-c > wget "https://github.com/linuxdeploy/linuxdeploy/releases/download/continuous/linuxdeploy-x86_64.AppImage"

# get list of variables
--help > ./linuxdeploy-plugin-gtk.sh

# first option: install your app into your AppDir via `make install` etc.
# second option: bundle your app's main executables manually
# see https://docs.appimage.org/packaging-guide/from-source/native-binaries.html for more information
> [...]

# call through linuxdeploy
--appdir > ./linuxdeploy-x86_64.AppImage AppDir --plugin gtk --output appimage --icon-file mypackage.png --desktop-file mypackage.desktop
```
