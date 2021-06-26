Mailhog Ansible Role
=========

Create [mailhog](https://github.com/mailhog/MailHog/) instance with support for multiple instances.

Requirements
------------

* debian based distribution

Example Playbook
----------------

```yaml
---
- name: Manage Docker Application Server
  hosts: docker.example.com
  remote_user: ansible
  become: true
  vars:
    ansible_python_interpreter: /usr/bin/python3
  roles:
    # full example
    - role: jindrichskupa.ansible_mailhog
      vars:
        # mailhog binary install dir, default `/opt/mailhog`
        mailhog_install_dir: /opt/mailhog
        # mailhog binary version, default `1.0.0`
        mailhog_version: 1.0.0
        # mailhog sendmail binary version, default `0.2.0`
        mhsendmail_version: 0.2.0
        # address to listen, default is all interfaces
        mailhog_listen_address: 0.0.0.0
        # SMTP port to listen, default is `1025`
        mailhog_smtp_port: 1025
        # Web UI port to listen, default is `8025`
        mailhog_http_port: 8025
        # Mail storage, default is memory, but you can use: memory / mongodb / maildir
        mailhog_storage: memory
        # in case you choose to use maildir as storage
        mailhog_maildir_path:
        # in case you choose to user mongodb as storage
        mailhog_mongo_host:
        mailhog_mongo_port:
        mailhog_mongo_collection:
    # just enough example
    - role: jindrichskupa.ansible_mailhog
      vars:
        mailhog_smtp_port: 1030
        mailhog_http_port: 9030
```

License
-------

MIT

Author Information
------------------

Jindrich Skupa
