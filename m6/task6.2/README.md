# Module 6. Linux Networking

### Hello. In this report, I want to present the sequence of actions that I followed to complete task 6.2 of the Linux Networking module, as well as the new technologies that I mastered in the process of implementation:

1) To perform task 2.6 of the modules 6, I’ve created 3 virtual machines: VM1 with enabled NAT and internal interface, VM2 and VM3 with internal only interfaces:
![stack Overflow](https://image.prntscr.com/image/t0SmknQiQkWu7SnQrdPrJg.png)
![stack Overflow](https://image.prntscr.com/image/jPSRGSIjTdqhCQrSch9AaQ.png)
![stack Overflow](https://image.prntscr.com/image/Nz2Sc_dST16Tf0Z0ZqBFYQ.png)
![stack Overflow](https://image.prntscr.com/image/gNOCyU5rR6ix7soyfJoBSg.png)

2) First of all I’ve configured DHCP server on VM1, as well as on VM2 and VM3, using VBoxManage by changing network to NAT Network and tested virtual machines by obtaining network address from DHCP:
![stack Overflow](https://image.prntscr.com/image/Q7Oe8iOKR_2XW7by2E0v1A.png)
![stack Overflow](https://image.prntscr.com/image/7u7cv1XNQdCHbaLqWOV1uQ.png)
![stack Overflow](https://image.prntscr.com/image/v2E2sIbwTXu5r8vaIk219A.png)

3) Also I’ve configured DHCP server via DNSMASQ on virtual machines:
- first of all I’ve installed it:
![stack Overflow](https://image.prntscr.com/image/HzaJQS5zSVOtbCidcljEQA.png)
- since the error occurred during installation due to port 53 was already busy, I’ve changed service port in dnsmasq config file, after that service has been restarted successfully on port 5300:
![stack Overflow](https://image.prntscr.com/image/PjHwGphTT8SPlcjqvdOMRQ.png)
![stack Overflow](https://image.prntscr.com/image/ZwDEh6TKTROkXUAkjsvhqg.png )
- I’ve configured DHCP service by editing configuration files /etc/network/interfaces and /etc/dnsmasq.com
![stack Overflow](https://image.prntscr.com/image/PP-yBkP5QLeCT-IeqE9ilg.png)
![stack Overflow](https://image.prntscr.com/image/8QlFs3p3Q7a9RW5OmWQGEw.png)
![stack Overflow](https://image.prntscr.com/image/8e6FEQnYT1yOYKhvbLUJAw.png)
- in similar way DHCP server was configured on VM2 and VM3:
![stack Overflow](https://image.prntscr.com/image/D5YyCIjeTw2DM1Zxdq141Q.png)

4) Also I’ve configured DNS server on virtual machine, using DNSMASQ. Configuration files /etc/resol.conf and /etc/dhcp/dhclient.conf were  edited:
![stack Overflow](https://image.prntscr.com/image/AGItuf-aQIi3l4-a71GoAw.png)
![stack Overflow](https://image.prntscr.com/image/_YqRTl0PSpauavKrNMokjw.png)

5) DNS server access test results on virtual machines:
![stack Overflow](https://image.prntscr.com/image/-SOqJTu6TQqK78AfqBUR7w.png)
![stack Overflow](https://image.prntscr.com/image/S450yUjqQU2wwAcNUKNYcQ.png)

### Thank you for attention!
