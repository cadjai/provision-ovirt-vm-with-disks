Role Name
=========

 This role is used to help provision and attach Disks for ovirt and RHV VMs. 

Requirements
------------
This was tested using the ovirtSDK 4.3 against RHV 4.3 using ansible 2.9

Role Variables
--------------
vm_hostname: The short hostname to assign to the VM being provisioned. It is will be used to composed the FQDN. 
vm_template: The Ovirt template being used to provision this VM
ovirt_cluster: Name of the ovirt cluster within the data center this is being provisioned.
vm_memory: The size of the RAM for the VM being provisioned in GiB
vm_cpucores: The number of virtual cores to assign to the VM being provisioned
vm_cpu: The number of CPU sockets being allocated to the VM being provisioned
vm_os: The Operating System of the image being used to provision this VM.
dns_server: The IP or FQDN of the DNS server to use for this VM if applicable
vm_dns_search: The DNS Search string to use for this VM. 
nic_boot_proto: The value of the NIC protocol to use for the VM (static, dhcp, none)
vm_host_subdomain: The subomain string to use for the FQDN of the VMif appliable.
base_domain: The base domain to apply to the VM for DNS resolution.
vm_user: The default user being provisioned with the VM. It can be the root user or any other user to provision with admin privileges
vm_rootpw: The password of the root user or the default admin user provisioned above
attach_additional_disks: Boolean to denote whethere extra disks are required to be provisioned for the VM. If false no additional Disks is added beyond the root/boot drive
additional_disks: Array of name and size of disks to add to the VM upon creation. Once added these disks are attached to the VM.

Mosts of the variables can be defined as group vars when creating groups of VM with similar profiles. 

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
