# Setup KVM on Ubuntu 20.04

Step 1:  Check if the system support virtualization. if the output of the following command is greater than zero (0), then the system support virtualization.<br>
<code>
  $ grep -Ec '(vmx|smx)' /proc/cpuinfo
</code>
* Step 2: Install KVM and dependencies.
<code>
  







