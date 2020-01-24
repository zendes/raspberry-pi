# Raspberry Pi

Latest image: `wget https://downloads.raspberrypi.org/raspbian_lite_latest`

## Headless configuration
```bash
# enable ssh daemon
touch /boot/ssh

# configure WiFi
cat <<EOF > /boot/wpa_supplicant.conf
country=US
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="NETWORK-NAME"
    psk="NETWORK-PASSWORD"
}
EOF
