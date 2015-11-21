install-docker
==============

It is a role for Ansible that can be used to
* Install Docker along with some python tools. These python tools are required for ansible modules 'docker' and 'docker_image'.
* Configure a non-root user to use docker without sudo.
* Run docker daemon.

Installation and usage
----------------------

Install with ansible-galaxy to the default roles location:

    ansible-galaxy install amidos.install-docker

...or to a custom location (subdirectory 'roles' in this example):

    ansible-galaxy install amidos.install-docker -p ./roles

And later in a playbook (user 'vagrant' is just an example):

    - hosts: servers
      roles:
        - { role: amidos.install-docker, docker_user: vagrant }

Role Variables
--------------

All variables are optional.

### Docker package

You probably wouldn't want to change these

* ```apt_key_url```
* ```apt_key_sig```
* ```apt_repository```

### User to use docker without sudo

* ```docker_user```
* ```docker_group```: It has to be 'docker'. So, don't change it, unless you know what you are doing.

### Docker configuration

* ```docker_opts```: Parameters for Docker daemon
* ```docker_tmpdir```: Path to tmp directory to be used by Docker
* ```docker_config_file```: Path to Docker config file (default is /etc/default/docker)
