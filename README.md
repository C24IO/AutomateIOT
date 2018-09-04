# AutomateIOT
Automate manual tasks needed to prep for - AWS ML IOT Labs

# Rough Notes

We want to automate the following - 

login as root - 

upsquared 
upsquared


rm -rfv /greengrass

userdel -r ggc_user
groupdel ggc_group

apt-get update
apt-get install -y wpasupplicant wireless-tools

iwconfig

mv /etc/network/interfaces /etc/network/interfaces.bck
touch /etc/network/interfaces

DATE_WITH_TIME=`date "+%m-%d-%Y-%H%M%S"`
echo "Created by Teensy on $DATE_WITH_TIME" > /etc/network/interfaces


echo "source /etc/network/interfaces.d/*" >> /etc/network/interfaces
echo "" >> /etc/network/interfaces
echo "# The loopback network interface" >> /etc/network/interfaces
echo "auto lo" >> /etc/network/interfaces
echo "iface lo inet loopback" >> /etc/network/interfaces
echo "" >> /etc/network/interfaces
echo "# The primary network interface" >> /etc/network/interfaces
echo "auto enp2s0" >> /etc/network/interfaces
echo "iface enp2s0 inet dhcp" >> /etc/network/interfaces
echo "" >> /etc/network/interfaces
echo "auto enp3s0" >> /etc/network/interfaces
echo "iface enp3s0 inet dhcp" >> /etc/network/interfaces

echo "" >> /etc/network/interfaces
echo "auto wlp4s0" >> /etc/network/interfaces
echo "iface wlp4s0 inet dhcp" >> /etc/network/interfaces
wpa_passphrase Guest Spheres@@2018 | grep -vE "{|#|}" | tr -d '\t' | tee -a /etc/network/interfaces
echo "" >> /etc/network/interfaces
echo "" >> /etc/network/interfaces


cat /etc/network/interfaces

/etc/init.d/networking restart

echo "nameserver 1.1.1.1" > /etc/resolv.conf

ping amazon.com





