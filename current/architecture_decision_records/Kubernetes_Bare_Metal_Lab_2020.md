* **Issue**: While on business for a month in Hawaii my home server went down. Turns out the PCIe mounted SATA SSD I installed Proxmox on failed. So I'm using this as an opportunity to rebuild my lab in the way I've been considering lately.

* **Decision**: I purchased another SATA SSD to reinstall a base OS on and four M.2 NVMe SSDs. My server has two PCIe 2.0 x16 slots so they should operate in x8 mode and still be more performant than running the VMs on my ZFS pool alongside the data.

On the SATA SSD, CentOS 8 will be my base OS. The four M.2 SSDs will be put into a second ZFS RAID 10 array that will be used as local backing storage orchestrated by Rook.

Calico & Istio CNI will be installed for virtual networking. Istio will be installed to manage network security, layer 7 routing, etc.

* **Constraints**: Kubernetes has been pretty fragile to me in the past. I've taken down my cluster a handful of times with simple package upgrades. Only having one node could mean more downtime in favor of better performance. It also could result in me treating my server more like a Pet than cattle and a resultant lack of attention to developing infrastructure as code.

* **Positions**: The other architectural model I could follow is reinstalling Proxmox on the new SATA SSD disk and using each of the four M.2 SSDs as backing storage for each VM-based node in the cluster.

* **Argument**: I decided to go with bare metal Kubernetes since I have had less and less of a reason to use VMs in the past year since I adopted Kubernetes in my lab. Performance is starting to become a bottleneck on my aging hardware so I need to gain performance where I can. Having all four M.2 disks operate in a ZFS RAID 10 means I will have a terabyte allocated as available storage to my pods. Rook will advertise this storage to the pods via a local storage class for significant performance gains over the existing NFS models. Especially around NFS.

* **Implications**: The entire lab needs to be rebuilt from scratch. I'm going to use this as an opportunity to move from Ansible/Jinja2 based deployments of applications to Kustomize as well. So significantly effort will be required to bring everything up.

Will also need to reevaluate ResourceLimits and Constraints more closely given how dangerous it could be to cause pressure on my new server. This is especially important given how much memory ZFS likes to take up. so realistically only around 30-40GB of memory will be available to my pods. A ballooning Plex instance could really wreak havoc on my server.

I also want to use this opportunity to move from BGP and VLANs for security to Istio. Istio is clearly the beneficial solution for building professional skills. And will allow for me to do a lot of cool things around Layer 7.

I also need to move my OpenVPN server to one of my single board computers instead of running it as a light VM on Proxmox. Shouldn't be an issue. They have like 5 9s of uptime right now with Arch Linux ARM.

* **Related decisions**: Is Calico the best CNI? Rook vs OpenEBS vs pure HostPath persistent storage.
