# ocp4-bootstrap
Deploy new openshift cluster on top vm, install ocp versi 4 pada virtual machine (HOW-TO)

My Lab Environment / Requirements
Server baremetal dgn spesifikasi sebagai berikut:
   - CPU 2 Socket 8 core
   - RAM Physical Memory 128GB
   - HDD storage 1TB

**ENVIRONMENT VARIABLES**
- OpenShift 4 Cluster base domain: premium.cluster							
- OpenShift 4 Cluster name: ocp4							
- OpenShift KVM network bridge: ovirtmgmt							
- OpenShift Network Block: 192.168.2.0/24							
- OpenShift Network gateway address: 192.168.2.1							
- Bastion / Helper node IP Address (Runs DHCP, Apache httpd, HAProxy, PXE, DNS)							
- NTP server used: time.google.com							
							
**HOSTNAME	MAC ADDR	IP ADDR (DHCP)	VCPU	MEMORY (MB)	DISK (GB)	OS	NOTES**

bastion		192.168.2.235	4	4096	150	Fedora-Server-dvd-x86_64-38-1.6.iso	Instance (Non-openshift)

bootstrap.ocp4.premium.cluster	52:54:00:c9:2a:23	192.168.2.40	4	16384	150	rhcos-live.x86_64.iso	Helpernode

master01.ocp4.premium.cluster	52:54:00:17:9b:11	192.168.2.41	8	16384	150	rhcos-live.x86_64.iso	Control plane

master02.ocp4.premium.cluster	52:54:00:35:71:cb	192.168.2.42	8	16384	150		

master03.ocp4.premium.cluster	52:54:00:6f:ac:ae	192.168.2.43	8	16384	150		

worker01.ocp4.premium.cluster	52:54:00:05:f4:37	192.168.2.44	6	8192	150	rhcos-live.x86_64.iso	Compute

worker02.ocp4.premium.cluster	52:54:00:0a:83:64	192.168.2.45	6	8192	150		

worker03.ocp4.premium.cluster	52:54:00:1a:2f:1f	192.168.2.46	6	8192	150	
