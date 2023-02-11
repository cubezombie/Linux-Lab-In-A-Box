# Linux Lab In A Box

- llab command to control lab functions on hypervisor. using ansible?
  - in /usr/local/bin
    - start
    - stop
    - rollback
    - snapshot
    - migrate (?)

- config dir LLAB
  - in /etc/
    - global variables
    - iso storage location
    - vm images location
    - kickstart file location
    - ftp location for rpms
    - dnsmasq config options
    - tftp config options
    - vsftp config options
    
- commands to run on vms only
  - register (RHEL)
  - adhoc (shortcut for ansible adoc command)
    - uptime (pull uptime from all vms)/var
    - release (detect lab vms version/release)
    
- Ansible playbooks/roles needed
  - firewalld
  - tftp
  - vsftpd
  - dnsmasq
  
- Config dirs
  - tftp
    - /var/lib/tftpboot
      - pxelinux.cfg - mac addresses of vms
        - 01-0e-b8-ae-4c-00-b6 - pxe boot menu for each vm
      - distro version directory (rhel79,fedora37,rhel95, etc)
        - initrd.img
        - vmlinuz
        
  - vsftpd
    - /var/ftp/pub
      - ks (kickstart directory contains base ks files)
        - rhel76-base-ks.cfg
        - rocky79-base-ks.cfg
        - centos79-base-ks.cfg
  
- RPMS/Packages needed
  - tree
