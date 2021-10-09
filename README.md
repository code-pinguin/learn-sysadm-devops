# Setup KVM on Ubuntu 20.04

Step 1:  Check if the system support virtualization. if the output of the following command is greater than zero (0), then the system support virtualization.<br>

`$ grep -Ec '(vmx|smx)' /proc/cpuinfo `

Step 2: Install KVM and dependencies.
<code>
 $ sudo apt install -y qemu qemu-kvm libvirt-daemon libvirt-clients bridge-utils virt-manager
</code>

  







