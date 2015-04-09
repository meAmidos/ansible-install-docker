install-docker
==============

It is a role for Ansible that can be used to
* Install Docker along with some python tools. These python tools are required for ansible modules 'docker' and 'docker_image'.
* Configure a non-root user to use docker without sudo.
* Run docker daemon.

Installation
------------

With ansible galaxy:

    ansible-galaxy install amidos.install-docker

And later in a playbook:

    - hosts: servers
      roles:
        - { role: amidos.install-docker, docker_user: vagrant }

Role Variables
--------------

### Docker package

You probably wouldn't want to change these

* ```apt_key_url```
* ```apt_key_sig```
* ```apt_repository```

### User to use docker without sudo

* ```docker_user```
* ```docker_group```: This is have to be 'docker'

### Additional

* ```docker_opts```: Parameters for docker daemon
