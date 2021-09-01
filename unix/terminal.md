# Terminal

## Count files in the folder:
```bash
ls | wc -l
```

## "You don't have write permissions for the /Library/Ruby/Gems/2.6.0 directory." Fix:
```bash
sudo gem install bundler
```


## Copy file via scp

```bash
scp archive.zip root@HOST_IP:~/Downloads
```

## Check who is using specified port
```bash
lsof -nP -iTCP:$PORT | grep LISTEN
```


## Change Lenovo conservation mode (requires sudo)


reading the current status:

```bash
cat /sys/bus/platform/drivers/ideapad_acpi/VPC2004:00/conservation_mode
```

enable Conservation mode:
```bash
echo 1  >  /sys/bus/platform/drivers/ideapad_acpi/VPC2004:00/conservation_mode
```

disable conservation mode:
```bash
echo 0  > /sys/bus/platform/drivers/ideapad_acpi/VPC2004:00/conservation_mode
```
