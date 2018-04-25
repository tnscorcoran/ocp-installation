### Instance size
```
t2.small for bastion
t2.large instance for master 
t2.large instance for node
```

### Storage

```
Master
/dev/sda1 50GB
/dev/sdb  50GB
/dev/sdc  80GB

Node
/dev/sda1 50GB
/dev/sdb  50GB
```

### Public IP and Route 53 settings

```
1) Assign Public IP to master ec2 instance

2) Crete Record set in Route 54
*.apps.summit
ocpmaster.summit
```