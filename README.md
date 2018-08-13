# Network-Diagram

My current Network Diagram is based around a Proxmox VE server that hosts both Docker containers and QEMU Virtual Machines. All public services are terminated by an NGINX Reverse Proxy. There are a multitude of physical devices, containers, and virtual machines present in the infrastructure.   


<p align="center">
   <img src="https://raw.githubusercontent.com/zimmertr/Network-Diagram/master/Proxmox_Lab_2018-Current.png" height="600">
</p>


Before moving to Proxmox, I used ESXi for years between vSphere 6.21 and 6.5. This labe principly consisted of physical devices and virtual machines, but I did occasionally dabble with containers on some Rancher hosts.   


<p align="center">
   <img src="https://raw.githubusercontent.com/zimmertr/Network-Diagram/master/ESXi_Lab_2016-2018.png" height="600">
</p>

All diagrams made with https://draw.io