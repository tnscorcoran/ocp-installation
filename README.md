# ocp-installation-non-HA


### Prepare hosts using ansible playbook

```
ansible-playbook -i host.prep host-prep.yml
```

### Replace with ansible hosts
Remember to add the new host file at location `/etc/ansible/hosts`

### Deploy cluster using ansible playbook

```
ansible-playbook -e openshift_disable_check=package_version,memory_availability,docker_storage /usr/share/ansible/openshift-ansible/playbooks/byo/config.yml
```

### Add user

```
htpasswd /etc/openshift/openshift-passwd user1
```