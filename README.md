generate-libvirt-vm
===================

KVM virtual Machines for Raspberry Pi 4 hosts via Ansible, libvirt and cloud templates.

This role creates a virtual machine which is then accesible via cloud-init drive setup.

Requirements
------------

Raspberry pi Running linux in 64 bits mode.

Currently this development has been done for Ubuntu 20.04.6 LTS but support to other targets might be done.

Role Variables
--------------

See [defaults/main.yml](defaults/main.yml) for optional and mandatory settings.

You may add a file `local-rpi4-${your-best-name}.yml` specifing the source for your preferred VM OS, see [vars/](vars/) files for the variables keys.


Dependencies
------------

This development has been made with ansible 2.10.5.

Example Playbook
----------------

    ---
    - hosts: all
      become: yes
      gather_facts: no
      vars:
        host_machine: rpi4
        guest_os: ubuntu-jammy
        vm_title: "ubuntu jammy 2023-10-15"
        cinit_password: h4ck3r!2
        cinit_authorized_keys:
          - ssh-rsa AAAAB3NzaC1ajNVw== foo@moon

    
      tasks:
        - include_role:
            name: generate-libvirt-vm
    

License
-------

BSD

Author Information
------------------

for -vvv info

Matías Pecchia
https://github.com/mabeett/
