# Fedora.conf
Fedora Linux configuration from scratch

## Preamble
1. Anything that is in a box like the one below is a command that should be run in a terminal.
	```
	example command that should be run in a terminal
	```
2. Most apps can also be installed from a graphical interface, using the **Software** app.

3. This guide is a work in progress. Please reffer to [the Fedora docs](https://docs.fedoraproject.org/en-US/docs/) for anything that's not included here.

## Basic Stuff
### Enabling 3rd party repositories
Enable the Free repository:
```
sudo dnf install \
https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm
```
Enable the Non-free repository:
```
sudo dnf install \
https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm
```
*enable both repositories (Non-free means closed-source, not payed)
### Installing GPU drivers
#### Nvidia drivers:
```
sudo dnf install akmod-nvidia
```
#### AMD drivers:
They should already be installed! (I think :P)
### Running apps/games on the dedicated GPU
For steam games, add ` %command%` at the end of every environment variable (right-click a game > Properties... > General > LAUNCH OPTIONS).
#### Nvidia:
For OpenGL games: `__NV_PRIME_RENDER_OFFLOAD=1 __GLX_VENDOR_LIBRARY_NAME=nvidia`

For Vulkan games: `__NV_PRIME_RENDER_OFFLOAD=1`
#### AMD:
Any app/game: `DRI_PRIME=1`
### GNOME extensions
- To enable GNOME extensions, install [this browser extension](https://extensions.gnome.org/about). A pop-up should appear, asking you to install it.
- Install **GNOME Tweaks**:
	```
	sudo dnf install gnome-tweaks
	```
- Search on the [GNOME extensions](https://extensions.gnome.org/) website to install extensions

	*Install the [User Themes](https://extensions.gnome.org/extension/19/user-themes/) extension if you want to use shell themes
## Installing other apps
### Minecraft
- First, we need java:
	```
	sudo dnf install java-17-openjdk.x86_64
	```
- Enable flatpak (**Software** > Hamburger Menu > Software Repositories > Apps (Flatpak) > enable the first 2 options)
- Search "Minecraft" and install the 4th one (the one that's just called "Minecraft")
