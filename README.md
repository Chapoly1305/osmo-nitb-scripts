
### RougeBTS

 This project is created for easy deployment of Osmocom GSM stack and convenient interaction with users

  - E(GPRS) support
  - Asterisk support
  - monitoring online subscribers
  - automatic interaction with new users, like sms, ussd or call
  - manual interaction with individual users
  - USSD-broadcast
  - SMS-broadcast
  - SMS-spam ;)


### Installation
Install the Prerequisites by reference to this tutorial. 
https://github.com/Ghost-Assassin/sdr/wiki/Running-osmo-nitb-on-LimeSDR-USB-with-Ubuntu-18.04


Install

```console
sudo apt install osmocom-nitb osmo-trx-lms osmo-bts-trx osmo-ggsn osmo-sgsn osmo-pcu osmo-sip-connector libsofia-sip-ua-glib-dev asterisk sqlite3 libsmpp1 telnet python3-pip
sudo pip3 install smpplib

```


Cloning Project

```console
git clone https://github.com/DrLafa/osmo-nitb-scripts
```


It is necessary to install Osmocom stack from apt, because it configure Systemd services. If you compile osmocom from sources, you need to install Systemd services by yourself with script `install_services.sh`

```console
sudo ./install_services.sh
```

Stopping launched services after installation
```console
sudo su
systemctl stop osmocom-nitb
systemctl stop osmo-nitb
systemctl stop osmo-trx-lms
systemctl stop osmo-bts-trx
systemctl stop osmo-ggsn
systemctl stop osmo-sgsn
systemctl stop osmo-pcu
systemctl stop osmo-sip-connector
systemctl stop asterisk
exit
```

Disabling service autostart
```console
sudo su
systemctl disable osmocom-nitb
systemctl disable osmo-nitb
systemctl disable osmo-trx-lms
systemctl disable osmo-bts-trx
systemctl disable osmo-ggsn
systemctl disable osmo-sgsn
systemctl disable osmo-pcu
systemctl disable osmo-sip-connector
systemctl disable asterisk
```


### Configure
All osmocom config files stored in `config/` folder and updating everytime when you start `main.py`. You can change it by youself.
