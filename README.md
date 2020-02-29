# Network-Diagram

<p align="center">
   <img src="https://raw.githubusercontent.com/zimmertr/Network-Diagram/master/current/diagrams/Kubernetes_Bare_Metal_Lab_2019.png" height="600">
</p>

[Architectural Decision Record](./current/architectural_decision_records/Kubernetes_Bare_Metal_Lab_2020.md)

<p align="center">
   <img src="https://raw.githubusercontent.com/zimmertr/Network-Diagram/master/current/diagrams/Kubernetes_Lab_2019.png" height="600">
</p>

As I continued developing my lab, I started moving more and more towards Kubernetes. This architecture is based around a Proxmox VE server that hosts both Docker containers and QEMU Virtual Machines. All public services are terminated by an NGINX Reverse Proxy. There are a multitude of physical devices, containers, and virtual machines present in the infrastructure.


<p align="center">
   <img src="https://raw.githubusercontent.com/zimmertr/Network-Diagram/master/old_diagrams/Proxmox_Lab_2018-2019/diagrams/Proxmox_Lab_2018-2019.png" height="600">
</p>


Before moving to Proxmox, I used ESXi for years between vSphere 6.21 and 6.5. This labe principly consisted of physical devices and virtual machines, but I did occasionally dabble with containers on some Rancher hosts.


<p align="center">
   <img src="https://raw.githubusercontent.com/zimmertr/Network-Diagram/master/old_diagrams/ESXi_Lab_2016-2018/ESXi_Lab_2016-2018.png" height="600">
</p>

All diagrams made with https://draw.io
