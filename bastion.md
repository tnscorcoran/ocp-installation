### Setting up Bastion host

```
subscription-manager register
subscription-manager list --available --matches 'Employee SKU' 
subscription-manager attach --pool=
subscription-manager repos --disable="*"
subscription-manager repos --enable="rhel-7-server-rpms" --enable="rhel-7-server-extras-rpms" --enable="rhel-7-server-ose-3.7-rpms" --enable="rhel-7-fast-datapath-rpms"
yum install atomic-openshift-utils -y
```

### Generating Keys

```
ssh-keygen -t rsa
cat ~/.ssh/id_rsa.pub
```