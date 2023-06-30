# setup-my-linux-2023

**In Ubuntu ! HEHEEEEEE**
## Terminal :
- Install Zsh
```sh
sudo apt install zsh
zsh --version
```
https://itsfoss.com/zsh-ubuntu/

- Setup Oh my Zsh :
...
## Remap my keyboard :
```
xev
// to know the keycode
//...
xmodmap -e "keycode  97 = less greater less greater bar brokenbar bar brokenbar"
// remap keycode to this value
```
## Fonts :
SF Pro
```
https://github.com/sahibjotsaggu/San-Francisco-Pro-Fonts/
```
SF Mono
```
https://github.com/supercomputra/SF-Mono-Font/
```
## Gnome Tweaks :
```sh
sudo apt install gnome-tweaks -y
```
- Themes :
  - Applications : WhiteSur-Light
  - Cursor : MacOs Cursor Set
  - Icons : MkOs-Big-Sur-Panel-white
  - Shell :
  - Sound : MacOs
- Fonts : 
  - Interface Text : SF Pro Text Regular 10 
  - Document Text : SF Pro Text Regular 10
  - Monospace Text : SF Mono Regular 10
  - Legacy Window Text : SF Pro Text Heavy 10
- Clock :
  - Date : ON
  - Second : ON

# Apple Color Emoji on Linux
1. Download font.
Check https://github.com/samuelngs/apple-emoji-linux/releases to get a link to the latest `AppleColorEmoji.ttf`

2. Put Apple Color Emoji on 1st place in 
```sh 
nano /etc/fonts/conf.d/60-generic.conf
```
```xml
...
	<alias binding="same">
		<family>emoji</family>
		<prefer>
			<family>Apple Color Emoji</family> <!-- Added -->
			<!-- System fonts -->
			<family>Noto Color Emoji</family> <!-- Google -->
			<family>Apple Color Emoji</family> <!-- Apple -->
			<family>Segoe UI Emoji</family> <!-- Microsoft -->
			<family>Twitter Color Emoji</family> <!-- Twitter -->
			<family>EmojiOne Mozilla</family> <!-- Mozilla -->
			<!-- Third-Party fonts -->
			<family>Emoji Two</family>
			<family>Emoji One</family>
			<!-- Non-color -->
			<family>Noto Emoji</family> <!-- Google -->
			<family>Android Emoji</family> <!-- Google -->
		</prefer>
	</alias>
...
```
3. Create font config:	
```bash	
mkdir ~/.config/fontconfig/	
nano ~/.config/fontconfig/fonts.conf
```
```xml
<?xml version="1.0" encoding="UTF-8"?>	
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">	
<fontconfig>	
  <alias>	
    <family>serif</family>	
    <prefer>	
      <family>Apple Color Emoji</family>	
    </prefer>	
  </alias>	
  <alias>	
    <family>sans-serif</family>	
    <prefer>	
      <family>Apple Color Emoji</family>	
    </prefer>	
  </alias>	
  <alias>	
    <family>monospace</family>	
    <prefer>	
      <family>Apple Color Emoji</family>	
    </prefer>	
  </alias>	
  <match target="pattern">	
    <test qual="any" name="family"><string>Noto Color Emoji</string></test>	
    <edit name="family" mode="assign" binding="same"><string>Apple Color Emoji</string></edit>	
  </match>	
</fontconfig>
```
4. Clear font cache:
```sh
fc-cache -f -v
```
## Gooogle Chrome
```
chrome://settings/fonts
```

### Font size : 
	`Tiny---(16)-------Huge`

### Minimum font size :
	`Tiny----(12)----Huge`

### Standard font: 
	`SF Pro Text 16`

### Serif font:
	`SF Pro Text 16`

### Sans-serif font:
	`SF Pro Text 16`

### Fixed-width font:
	`SF Mono 13`

### Mathematical font:
	`SF Pro Text 16`
