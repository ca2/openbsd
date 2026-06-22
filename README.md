# openbsd


doas mkdir -p /etc/X11/xorg.conf.d

/etc/X11/xorg.conf.d/50-vmmouse.conf

Section "InputClass"
   Identifier "VMware vmmouse"
   MatchIsPointer "on"
   Driver "vmmouse"
EndSection
EOF


/etc/X11/xorg.conf.d/10-vmware-video.conf

Section "Screen"
	DefaultDepth 24
	Identifier "Screen0"
	Device "Card0"
	Monitor "Monitor0"

	SubSection "Display"
		Viewport 0 0
		Depth 24
		Modes "1920x1080"
	EndSubSection

EndSection



GNOME at OpenBSD 7.9
As the GUI seems not to work for many things, including settings (and also Keyboard settings), here are some commands to change settings




At Terminal I think it is important to ask for “Run command as a login shell”.

gsettings set org.gnome.desktop.input-sources sources "[('xkb', 'br'), ('xkb', 'dk')]"
gsettings set org.gnome.desktop.screensaver lock-enabled false
gsettings set org.gnome.desktop.session idle-delay 0
gsettings set org.gnome.desktop.interface clock-format '24h'
gsettings set org.gnome.desktop.interface clock-show-weekday true
gsettings set org.gnome.desktop.interface clock-show-seconds true
gsettings set org.gnome.desktop.calendar show-weekdate true

gsettings set org.gnome.settings-daemon.plugins.power sleep-inactive-ac-type 'nothing'
