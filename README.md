# Setup KVM on Ubuntu 20.04

Step 1:  Check if the system support virtualization. if the output of the following command is greater than zero (0), then the system support virtualization.

`$ grep -Ec '(vmx|smx)' /proc/cpuinfo `

Step 2: Install KVM and dependencies.

`$ sudo apt install -y qemu-kvm libvirt-daemon libvirt-daemon-system libvirt-clients bridge-utils cpu-checker`
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
Step 5: Verify Installation

````
$ virsh list
 Id   Name   State
--------------------

````



 







