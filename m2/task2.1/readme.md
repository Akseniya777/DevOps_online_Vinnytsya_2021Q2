# Hello,

#### Hypervisor is a technology for deploying software on physical hardware using virtualization.
#### There are two main types of hypervisors. Hypervisors of the first type (this includes Hyper-V, KVM, ESXi solutions) work at the hardware level without the need to install any OS on the host. Therefore, they are also called hardware. Hypervisors of the second type (VMware Workstation, Oracle Virtual Box, OpenVZ) need an OS to access the virtual machine monitor to the host's hardware resources.

#### I would like to present my report on task 2.1 of module 2 implementation.

### Here is the sequences of actions I've performed, some difficulties I've faced with and new things I've learned during it's execution:

## WORK WITH VIRTUALBOX

* I’ve successfully installed and launched the latest version of VirtualBox on my laptop with Ubuntu 18.03, and created my first virtual machine: 
![stack Overflow](https://image.prntscr.com/image/gEr-hJfYTgyaAKAKLCtSzA.png)
![stack Overflow](https://image.prntscr.com/image/6_Dw7Lk2Srypi2Zv1_JUAA.png)

* Downloaded the latest version of Ubuntu - Ubuntu 21, attached Ubuntu snapshot to virtual disk and run the installation:
![stack Overflow](https://image.prntscr.com/image/GT3kNN_xTmqkSpVExtNe2w.png)
![stack Overflow](https://image.prntscr.com/image/toqPJtnXTq_Bc2xKtPo55w.png)
![stack Overflow](https://image.prntscr.com/image/bwStiVuWRmaPHIR8PepJzQ.png)
![stack Overflow](https://image.prntscr.com/image/PhUfQzkgR1myEHqgsuwheQ.png)
![stack Overflow](https://image.prntscr.com/image/bZoQuRIgRfqnIbLImEoUDg.png)
And got acquainted with the possibilities of VM1 control - start, stop, reboot, save state

* After the first start of virtual machine there was a black screen, and in settings displayed the following error:
![stack Overflow](https://i.imgur.com/e6t9IbL.png)
Thus, in order to resolve:
I’ve installed VirtialBox Extension pack:
![stack Overflow](https://image.prntscr.com/image/XHxxFyLrQ8aXMA-Lsq2BCw.png)
![stack Overflow](https://image.prntscr.com/image/0RBfzE1kQQaPjduMjrSuMQ.png")
I’ve increased base memory from 1024 to 2048 MB, video memory from 16 to 100 MB, and CPU units from 1 to 3, this has helped to start machine without issues and display work fine as well:
![stack Overflow](https://image.prntscr.com/image/KKmdLzyNSyihZSOuoYUTXA.png)

* I’ve successfully cloned my existing VM1_Pobidash machine by creating a VM2_Pobidash, after that have created a group of these 2 virtual machines:
![stack Overflow](https://image.prntscr.com/image/hA_iDZZvQmeA050lZ_9zQw.png)
![stack Overflow](https://image.prntscr.com/image/Tqq_sz4GS1ap2mCOQr47Ww.png)
![stack Overflow](https://image.prntscr.com/image/idAtQ_jmQb6y8RbWZgN6Kg.png)
![stack Overflow](https://image.prntscr.com/image/3Cxrd8qlT-yXrgFrDR3I5A.png)

* For VM1, I've created a several different snapshots:
![stack Overflow](https://image.prntscr.com/image/XsAF2eEyQ92s-Ie1Rsmg7w.png) 

* Have exported and imported VM1 as *.ova file:
![stack Overflow](https://image.prntscr.com/image/AVb9sWNxQl_QGjWNKr-7CA.png)
![stack Overflow](https://image.prntscr.com/image/vNrrszHlS2mukaCApkGzWw.png)

* I’ve enabled USB support for VM in virtual machine settings, as well as added my admin user to vbox users:
![stack Overflow](https://image.prntscr.com/image/_fsoWZJmSze56UyV9O7hdg.png)

But USB device was not recognized still on guest machine, so that is why I’ve added it manually:
![stack Overflow](https://image.prntscr.com/image/6eGS0KsiShKhDbsNu1bslw.png)
![stack Overflow](https://image.prntscr.com/image/lOlVuTSaT3C4idyjsySK5A.png)

* I've configured a shared folder to exchange data between the virtual machine and the host
![stack Overflow]()
https://prnt.sc/18yynlc 

* Have configured  different  network  modes  for  VM1,  VM2 and checked  the  connection between VM1, VM2, Host, Internet for different network modes using ping command to do this. Here are pissible connections:
Mode	VM→Host	VM←Host	VM1↔VM2	VM→Net/LAN
Host-only	https://prnt.sc/18z61j0	https://prnt.sc/18z6hrr	https://prnt.sc/18z9837	https://prnt.sc/18z9in4
Internal	https://prnt.sc/18z9vpc	https://prnt.sc/18za1r8	https://prnt.sc/18zb38h	https://prnt.sc/18zb7h4
Bridged	https://prnt.sc/18zbko6	https://prnt.sc/18zbv3x	https://prnt.sc/18zc4sd	https://prnt.sc/18zca0g
NAT	https://prnt.sc/18zclg0	https://prnt.sc/18zd89g	https://prnt.sc/18zdr7m	https://prnt.sc/18zdw3i

* The  basic  commands  of  VBoxManage and it's purpose:

> to view the list of created virtual machines:
> ![stack Overflow](https://image.prntscr.com/image/RfdAsXNsQDGDlW14NuzUfQ.png)

> to view info of particular machine:
> ![stack Overflow](https://image.prntscr.com/image/4VCxmEtNRE2CVHo6PB2eoQ.png)

> to create new virtual machine:
> ![stack Overflow](https://image.prntscr.com/image/2e09NYotTLeM5OQ316mH0A.png)

> to start virtual machine:
> ![stack Overflow](https://image.prntscr.com/image/oUdwKPEmTji0fZgHQEdV1w.png)

> to change VM status:
> ![stack Overflow](https://image.prntscr.com/image/Gi3o8Wz9TPCdp42qI9tvsA.png)

> to change VM parametres:
> ![stack Overflow](https://image.prntscr.com/image/QOdnJT3lTAGNLvRr_3YQrQ.png)


## WORK WITH VAGRANT

* I've downloaded and installed the required version of Vagrant according to the instructions and to  the  host  operating  system

* Have created the folder with my name, wen t to the folder and unitialized the environment with the default Vagrant box:
![stack Overflow](https://image.prntscr.com/image/SSVN_PDTRJa2sN9gqAAR-g.png)

* Run vagrant up and watch for messages during VM boot and startup:
![stack Overflow](https://image.prntscr.com/image/PGJFmrHdR5ibC9J5U68xyg.png)

* I've connectedt to  the  VM  using  SSH terminal by entering username, IP address and port listed (127.0.0.1:2222), and recorded the date and time by executing the date command:
![stack Overflow](https://image.prntscr.com/image/IIQGD_YNSH_kVDBBkvmFSQ.png)

* Have stopped and deletet the created VM:
![stack Overflow](https://image.prntscr.com/image/e6rQdnO9RXeyUck3pEnM6w.png)



