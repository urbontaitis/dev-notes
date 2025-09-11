# Mac OS

```bash
# Fixing keyboard typing issues: e.g. while pressing ` print outs ±
sudo open /System/Library/CoreServices/KeyboardSetupAssistant.app/Contents/MacOS/KeyboardSetupAssistant
```
>Source [http://m10lmac.blogspot.com/2009/12/fixing-keyboard-type-problems.html](http://m10lmac.blogspot.com/2009/12/fixing-keyboard-type-problems.html)



## Reboot into recovery via terminal
```bash
sudo nvram "recovery-boot-mode=unused"
sudo reboot

# back to normal
nvram -d recovery-boot-mode
```

## iPhone hotspot issue with FortiClient and IPV6

You need to disbale IPv6 on Wi-Fi adapter:
```bash
sudo networksetup -setv6off Wi-Fi
```

# To verify configuration:
```bash
networksetup -getinfo Wi-Fi
```
