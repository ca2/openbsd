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

