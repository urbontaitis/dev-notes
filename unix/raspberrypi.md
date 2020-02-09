# Raspberry Pi

```bash
# Raspberry Pi Model Information
cat /proc/device-tree/model

# Finding the Pi Revision Number by reading the "cpuinfo":
 cat /proc/cpuinfo

 # New raspberrypi versions:
 pinout
```
> Source [https://www.raspberrypi-spy.co.uk/2012/09/checking-your-raspberry-pi-board-version/](https://www.raspberrypi-spy.co.uk/2012/09/checking-your-raspberry-pi-board-version/)

## Installing Golang
```bash
# As of Go 1.6 (February 2016), an official ARMv6 package is available for download. So, if your Raspberry Pi has ARMv6 or v7 (see cat /proc/cpuinfo | grep ARM), then just do something like:

wget https://storage.googleapis.com/golang/go1.6.2.linux-armv6l.tar.gz 
sudo tar -xzf go1.6.2.linux-armv6l.tar.gz -C /usr/local
sudo chgrp -R staff /usr/local/go
export GOROOT=/usr/local/go
export PATH="$PATH:$GOROOT/bin"

```
> Source [https://raspberrypi.stackexchange.com/a/46828](https://raspberrypi.stackexchange.com/a/46828)

## Run raspberry pi in virtual machine
```bash
brew install qemu
# First, create a folder for your VMs and move the image in
sudo mkdir ~/qemu/
mv ~/Downloads/IMAGE.iso ~/qemu/
cd ~/qemu
# Now let’s launch the image in qemu with the following command:
qemu-system-x86_64 -hda IMAGE.iso -m 1024 -net nic -net user
```
> Source [https://raspberrytips.com/run-raspberry-in-virtual-machine/](https://raspberrytips.com/run-raspberry-in-virtual-machine/)

## Running services on Raspberry pi
```bash
#Service example
vi /home/dani/scripts/tempMonitor/tempMonitor.service

[Unit]
Description=Raspberry Temperature Monitor
After=network-online.target

[Service]
ExecStart=/bin/bash /home/dani/scripts/tempMonitor/tempMonitor.sh
WorkingDirectory=/home/dani/scripts/tempMonitor/
StandardOutput=inherit
StandardError=inherit
Restart=always
User=dani

[Install]
WantedBy=multi-user.target

```
> Source and example of IFTT integration [https://domoticproject.com/creating-raspberry-pi-service/](https://domoticproject.com/creating-raspberry-pi-service/)

```bash
# Get status about why service failed:
	journalctl -u tv.service

# copy service
sudo cp /home/pi/example.service /lib/systemd/system/

sudo systemctl enable example.service
```

## Systemd: Run it last 
[https://www.mauras.ch/systemd-run-it-last.html](https://www.mauras.ch/systemd-run-it-last.html)
