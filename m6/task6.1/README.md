# Module 6. Linux Networking

### Hello. In this report, I want to present the sequence of actions that I followed to complete task 6.1 of the Linux Networking module, as well as the new technologies that I mastered in the process of implementation:

1) To perform task 6.1 of module 6, I used 2 installed virtual machines with Oracle VirtualBox, both with Ubuntu 21.
On the first virtual machine VM1_Pobidash I’ve enabled 2 interfaces - NAT and internal:
![stack Overflow](https://image.prntscr.com/image/DH96UOOeS1mrX7Oikg_DHQ.png)
![stack Overflow](https://image.prntscr.com/image/QTcZRXFtSL6TzdVhDk4mJw.png)
On the second virtual machine VM2_Pobidash only 1 interface has been enabled - internal:
![stack Overflow](https://image.prntscr.com/image/Gf4Qrau-TU2GYe9ydzp6Ig.png)

2) Then I’ve starter to configure network interface on VM2_pobidash virtual machine:
- at the beginning there were no access to the internet:
![stack Overflow](https://image.prntscr.com/image/dpBSQHB_QwOORGjK3d0FYA.png)
- since I’ve decided to configure network interface  vi /etc/network/interfaces file, first of all I’ve installed network tools packages on my Ubuntu virtual machine:
![stack Overflow](https://image.prntscr.com/image/dhhAQ3WBQA6gsgeOrkdtVA.png)
- secondly, since I wanted to set static IP address for machine, first of all I’ve checked network card using ‘ifconfig’ command:
![stack Overflow](https://image.prntscr.com/image/HvzjkNDaSgiVUx9U3s1AIQ.png)
- finally, I’ve edited /etc/network/interfaces file:
before changes:
![stack Overflow](https://image.prntscr.com/image/A_3CtA4ETq-2CxpVtn7a2A.png)
after changes:
![stack Overflow](https://image.prntscr.com/image/MmtHTocxQASbbVxbJpY-VQ.png)
- after network service restarting using ‘sudo service networking restart’ command and virtual machine rebooting, the new static IP address of the machine has been displayed:
![stack Overflow](https://image.prntscr.com/image/uceWBHxJQzODUOXtutEo7w.png)
- also I’ve changed server hostname by editing /etc/hostname and /etc/hosts file:
![stack Overflow](https://image.prntscr.com/image/jLv5-daERP2wgIGV4ylqeg.png)
![stack Overflow](https://image.prntscr.com/image/Oz815cSmR9257JiEv2NrEw.png)
- have enabled port forwarding from guest machine to host machine and tested it:
![stack Overflow](https://image.prntscr.com/image/-JpoeFNERUSjoZ1NyTs1rA.png)
![stack Overflow](https://image.prntscr.com/image/jVAvHulrQ0KafpLuht7Ttg.png)
- have added iptables rules:
![stack Overflow](https://image.prntscr.com/image/dnvfbf65RZSmBx_OqgXozg.png)

3) After configuring network interface, I’ve troubleshooted network state using specific network utilities:
- I’ve checked the route from virtual machine to host, using ‘traceroute’ utility:
![stack Overflow](https://image.prntscr.com/image/nbIg0ghOQXOXjA6b7F3nkw.png)
- also I’ve checked access to the internet, using ‘ping’ command:
![stack Overflow](https://image.prntscr.com/image/vHl61ctLSRmQVBQwVUqIrA.png)
- with the help of ‘nslookup’ utility I’ve determined the IP address belongs to resource epam.com:
![stack Overflow](https://image.prntscr.com/image/foyEWDxdTE6X_Eor51uDbw.png)
- using ‘traceroute’ utility, I’ve determined the resources of IP address 8.8.8.8:
![stack Overflow](https://image.prntscr.com/image/MmYdnR9sTTKL-K-ECcsP7w.png)
- also I’ve determined default gateway to my host and displayed routing table using ‘route’ command:
![stack Overflow](https://image.prntscr.com/image/u7wyiuYhQO6IYpnisxkGzA.png)
- as well as have performed trace route to google.com:
![stack Overflow](https://image.prntscr.com/image/m7S_28DaRmeUImjOOgYMWQ.png)

### Thank you for attention!
