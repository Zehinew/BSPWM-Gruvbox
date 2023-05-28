# Dotfiles
##Installing for BSPWM
#KEYBOARD---------------------------------------------------------------------------------------
sudo nano /etc/X11/xorg.conf.d/00-keyboard.conf

Section "InputClass"
    Identifier "system-keyboard"
    MatchIsKeyboard "on"
    Option "XkbLayout" "us,ru"
    Option "XkbModel" "pc105"
    Option "XkbOptions" "grp:alt_shift_toggle"
EndSection

#BSPWM INSTALL-----------------------------------------------------------------------------------

sudo pacman -S xorg xorg-xinit mesa bspwm git base-devel sxhkd alacritty

.xinitrc:
exec sxhkd &
exec bspwm

chmod u+x .config/bspwm/bspwmrc

#SOFT---------------------------------------------------------------------------------------------

sudo pacman -S pulseaudio pavucontrol mpv gimp inkscape telegram-desktop lxappearance nitrogen imv
obs-studio python thunar tumbler jq polybar awesome-terminal-fonts rofi

#TERMINAL SOFT-----------------------------------------------------------------------------------

sudo pacman -S htop links cmus neofetch cava ueberzug w3m

#YAY---------------------------------------------------------------------------------------------

git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si

#PICOM------------------------------------------------------------------------------------------

yay picom-jonaburg-git

#CHROME-----------------------------------------------------------------------------------------

yay -S google-chrome

#FONT------------------------------------------------------------------------------------------

yay -S nerd-fonts ttf-jetbrains-mono ttc-iosevka

#SDDM------------------------------------------------------------------------------------------

yay -S sddm sddm-theme-corners-git

nano /urs/lib/sddm/sddm.conf.d/default.conf
#Theme=corners
