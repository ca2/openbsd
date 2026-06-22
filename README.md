# openbsd


doas mkdir -p /etc/X11/xorg.conf.d

doas tee /etc/X11/xorg.conf.d/50-vmmouse.conf >/dev/null <<'EOF'
Section "InputClass"
   Identifier "VMware vmmouse"
   MatchIsPointer "on"
   Driver "vmmouse"
EndSection
EOF


doas tee /etc/X11/xorg.conf.d/10-vmware-video.conf >/dev/null <<'EOF'
Section "Device"
   Identifier "VMware SVGA"
   Driver "vmware"
   Option "GuiLayout" "1920x1080+0+0"
EndSection
