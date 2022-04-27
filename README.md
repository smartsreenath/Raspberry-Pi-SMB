<p align="center">
  <img 
    width=50%
    height=50%
    src="https://i.imgur.com/b04QAsB.png"
  >
</p>

# Raspberry Pi network-attached storage (NAS) Server—3rd  Part
### Raspberry Pi SMB (SAMBA on RPI)



![YouTube](https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white)![Raspberry Pi](https://img.shields.io/badge/-RaspberryPi-C51A4A?style=for-the-badge&logo=Raspberry-Pi)![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)![Windows](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)![Mac OS](https://img.shields.io/badge/mac%20os-000000?style=for-the-badge&logo=macos&logoColor=F0F0F0)![IOS](https://img.shields.io/badge/iOS-000000?style=for-the-badge&logo=ios&logoColor=white)![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)

### What is NAS ?

Network-attached storage (NAS) allows you to save files from your computer and mobile devices to external hard drives via your home or office wireless network.
There are plenty of ready-built NAS devices out there, from companies such as Synology, QNAP, and Asustor. But they can get expensive.
The Raspberry Pi, on the other hand, is such a versatile little board that it can act as a cheap NAS.
### Choosing the right Raspberry Pi and accessories
The faster your Raspberry Pi, the faster your data will save to your external storage. For this reason, I recommend using a Raspberry Pi 4 with atleast 2gb RAM.

### Even though you have perefectly running OS installed in Raspberyy pi, I recommend you go through below tutorials
 - https://github.com/smartsreenath/Raspberry-Pi-VNC-Install/blob/main/README.md (1st Part)
- https://github.com/smartsreenath/Raspberry-Pi-SSD-BOOT (2nd Part)

1. Before proceeding we have to make sure that our pi os is running with new updates
2. Type the below commands (I am assuming that you have VNC and SSH enabled. if not go through above tutorials)
```sh
sudo apt update
```
```sh
sudo apt full-upgrade
```
6.	Type “Y” for yes
7.	Reboot PI, Type
```sh
sudo reboot now
```
3. Next is installing SAMBA on RPI, Open terminal
```sh
sudo apt-get install samba 
```
4.	Enter “Y”  When prompted
5.	Reboot RPI
```sh
sudo reboot now
```
6. Next  we have to modify Samba Configuration file, in order to do that open terminal
```sh
sudo nano /etc/samba/smb.conf
```

![This is an image](https://i.imgur.com/jjnlJ4r.jpg)

7.	Add below text at the end of the line.. 
(I am going to make this folder read and write for everyone.)
```sh
[Pi-Share]
    path = /home/pi/Pi-Share
    read only = no
    public = yes
    writable = yes
```
![This is an image](https://i.imgur.com/ho3x53G.jpg)

8.	Press “CONTROL + O” to write  and then hit “Enter” to save the file
9.  Next we to make share folder, I am going to create in the home/pi directory 
###  (Or you can resize SSD, make another partition and create a share folder on that partition. To make this tutorial simple, I am going to create a folder here.  )
10. I am going to name the folder Pi-Share

![This is an image](https://i.imgur.com/eaRYGfQ.jpg)

11. Next we need to change permission, for that you have to right click and select permission, then change drop down menu according pic. (I am going to make this folder read and write for everyone.)

![This is an image](https://i.imgur.com/qdteeko.jpg)

12. click "ok"
13. Then click confirm "yes"
#### Windows 10 / Windows 11
14. Next in PC, you need to map the network location in order to access
15. Right click in This PC (Windows 10 / windows 11)
16. Select Add a network location

![This is an image](https://i.imgur.com/4K2Qn30.jpg)

17. Click "next"
18. Click "next" (choose a custom network location)
19. Type the IP address of pi + name of the share folder (internet or network address)
20. Mine look like this

![This is an image](https://i.imgur.com/OcryYke.jpg)

21. Click next
22. Rename the Folder.

![This is an image](https://i.imgur.com/D5PtikB.jpg)

23. That is it.. enjoy


