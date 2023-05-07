# Setup KVM on Ubuntu 22:04:

Step 1:  Check if the system support virtualization. if the output of the following command is greater than zero (0), then the system support virtualization.

`$ grep -Ec '(vmx|smx)' /proc/cpuinfo `

Step 2: Install KVM and dependencies (Ubuntu 22.04).

`sudo apt install qemu qemu-kvm libvirt-daemon libvirt-daemon-system virtinst libvirt-clients bridge-utils cpu-checker`
````
$ kvm-ok
INFO: /dev/kvm exists
KVM acceleration can be used
````
 
* qemu-kvm package -main KVM package.
* libvirtd-daemon, libvirtd-daemon-system -virtualization daemon.
* bridge-utils package - create a bridge connection for networking.

Step 3: Start and enable libvirtd

`$ sudo systemctl start libvirtd && sudo systemctl enable libvirtd`

Step 4: Verify status of libvirtd

````
$ sudo systemctl status libvirtd
libvirtd.service - Virtualization daemon
     Loaded: loaded (/lib/systemd/system/libvirtd.service; enabled; vendor preset: e>
     Active: active (running) since Sat 2021-10-09 13:15:16 PST; 7min ago
TriggeredBy: ● libvirtd-ro.socket
             ● libvirtd.socket
             ● libvirtd-admin.socket
       Docs: man:libvirtd(8)
             https://libvirt.org
   Main PID: 11409 (libvirtd)
      Tasks: 19 (limit: 32768)
     Memory: 12.1M
     CGroup: /system.slice/libvirtd.service
             ├─ 4370 /usr/sbin/dnsmasq --conf-file=/var/lib/libvirt/dnsmasq/default.>
             ├─ 4371 /usr/sbin/dnsmasq --conf-file=/var/lib/libvirt/dnsmasq/default.>
             └─11409 /usr/sbin/libvirtd

Oct 09 13:15:16 E5470 systemd[1]: Starting Virtualization daemon...
Oct 09 13:15:16 E5470 systemd[1]: Started Virtualization daemon.
Oct 09 13:15:16 E5470 dnsmasq[4370]: read /etc/hosts - 7 addresses
Oct 09 13:15:16 E5470 dnsmasq[4370]: read /var/lib/libvirt/dnsmasq/default.addnhosts>
Oct 09 13:15:16 E5470 dnsmasq-dhcp[4370]: read /var/lib/libvirt/dnsmasq/default.host>
````
Step 5: Add Your User to the KVM and Libvirt Group

 `$ sudo usermod -aG kvm $USER`
 `$sudo usermod -aG libvirt $USER`
 

````
$ virsh list
 Id   Name   State
--------------------

````

#  Setup Vagrant on Ubuntu 20.04

 TODO: Add setup for Vagrant on local computer

# Setup Jenkins on virtual machine

 TODO:  Add setup for Jenkins

# Setup Jenkins on AWS EC2 Instance

 TODO:  Add setup for Jenkins on AWS EC2 Instance
 
 # Setup Jenkins on Docker

 TODO:  Add setup for Jenkins on Docker

#  Setup for Tomcat on AWS EC2 Instance

 TODO:  Add setup for Tomcat9 on AWS EC2 Instance

 







