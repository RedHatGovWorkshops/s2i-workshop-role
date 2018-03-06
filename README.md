S2I Workshop Role
=========

This role configures the OpenShift Container Platform for an S2I workshop.

Requirements
------------

This role requires an OpenShift Container Platform 3.7+ cluster.  This role assumes access to a host with the **oc** CLI tool.

Role Variables
--------------

```yaml
---
---
# defaults file for s2i-workshop-configure-role
# The project in which to deploy the gochat-server
server_project: gochat-server
# The Golang S2I repo
golang_s2i_repo: https://github.com/RedHatGovWorkshops/golang-s2i
# The Golang Template
golang_template: https://raw.githubusercontent.com/RedHatGovWorkshops/golang-s2i/master/templates/golang.yml
# The Gochat server repository
gochat_server_repo: https://github.com/RedHatGovWorkshops/openshift-gochat-server
# Keep all chat traffic internal
internal_chat_traffic: yes
```


Example Playbook
----------------
```yaml
- name: Workshop S2I | S2I Workshop Configure
  hosts: openshift_masters
  become: yes
  roles:
    - s2i-workshop-role
```
License
-------

GPLv3

Author Information
------------------

Ken Evensen is a Solutions Architect with Red Hat.
