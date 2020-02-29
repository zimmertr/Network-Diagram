# Network-Diagram

## Kubernetes Focused



<p align="center">
   <img src="https://raw.githubusercontent.com/zimmertr/Network-Diagram/master/current/diagrams/Kubernetes_Bare_Metal_Lab_2019.png" height="600">
</p>


[Architectural Decision Record](./current/architectural_decision_records/Kubernetes_Bare_Metal_Lab_2020.md)


## Kubernetes Focused

As I continued developing my lab, I started moving more and more towards Kubernetes. This architecture is based around a Proxmox VE server that hosts both Docker containers and QEMU Virtual Machines. All public services are terminated by an NGINX Reverse Proxy. There are a multitude of physical devices, containers, and virtual machines present in the infrastructure.

My current network is based around Kubernetes which is hosted on Proxmox. QEMU is all but phased out at this point aside from running the nodes themselves. Eventually I intend to migrate to bare metal nodes and avoid virtualization all together. But for now, cost is an issue. Still terminating public services with NGINX, but now it's hosted on GCE. Hardware networking is all Ubiquiti stuff. Also have two Odroid XU4 Single Board Computers which run some production-level networking stuff like DNS, Unifi Controller, and Ad Blocking. That way when I have downtime in my Kubernetes cluster my network no longer suffers. VLANs have also been fully incorporated within the network, and split it into 7 specific areas to partition broadcast traffic and increase security.

<p align="center">
   <img src="https://raw.githubusercontent.com/zimmertr/Network-Diagram/master/old_diagrams/Kubernetes_Lab_2019-2020/diagrams/Kubernetes_Lab_2019-2020.png" height="600">
</p>


## Docker Focused

This phase of the network was based around a Proxmox VE server that hosts both Docker containers and QEMU Virtual Machines. All public services are terminated by an NGINX Reverse Proxy. There are a multitude of physical devices, containers, and virtual machines present in the infrastructure.

<p align="center">
   <img src="https://raw.githubusercontent.com/zimmertr/Network-Diagram/master/old_diagrams/Proxmox_Lab_2018-2019/diagrams/Proxmox_Lab_2018-2019.png" height="600">
</p>



## ESXi/VM Focused

Before moving to Proxmox, I used ESXi for years between vSphere 6.21 and 6.5. This labe principly consisted of physical devices and virtual machines, but I did occasionally dabble with containers on some Rancher hosts.

<p align="center">
   <img src="https://raw.githubusercontent.com/zimmertr/Network-Diagram/master/old_diagrams/ESXi_Lab_2016-2018/ESXi_Lab_2016-2018.png" height="600">
</p>

All diagrams made with https://draw.io
