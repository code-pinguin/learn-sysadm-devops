# Setup KVM on Ubuntu 20.04

Step 1:  Check if the system support virtualization. if the output of the following command is greater than zero (0), then the system support virtualization.

`$ grep -Ec '(vmx|smx)' /proc/cpuinfo `

Step 2: Install KVM and dependencies.

 `$ sudo apt install -y qemu-kvm libvirt-daemon libvirt-daemon-system libvirt-clients bridge-utils cpu-checker`
 
* qemu-kvm package -main KVM package.
* libvirtd-daemon, libvirtd-daemon-system -virtualization daemon.
* bridge-utils package - create a bridge connection for networking.

Step 3: Start and enable libvirtd


  







