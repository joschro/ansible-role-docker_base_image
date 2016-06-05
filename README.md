Docker Base Image
=================

Create a docker base image for yum/dnf based linux distributions like CentOS, Fedora or RHEL.
The tool used for creation is located here:
```
https://github.com/docker/docker/blob/master/contrib/mkimage-yum.sh
```

Requirements
------------

The Docker service should be installed and running; you may want to use the Ansible role dockerhost from
```
https://github.com/joschro/ansible-role-dockerhost
```

Role Variables
--------------

None.

Dependencies
------------
```
https://github.com/joschro/ansible-role-dockerhost
```

Example Playbook
----------------
```
- name: Create a Docker base image
  hosts: dockerhosts
  remote_user: root

  roles:
    - docker_base_image
```

After running this playbook, you can run the docker image with
```
docker images
docker run -t -i [name-of-your-image]:[tag-of-your-image] /bin/bash
- or -
docker run -t -i [image-id] /bin/bash
```
You can now start typing shell commands within your docker image.

License
-------

GPLv3

Author Information
------------------

Joachim Schröder, jos (at) redhat.com

