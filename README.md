# Deploy docker swarm roles

Swarm nodes in proxmox cluster:
```sh
192.168.160.200 swarm-node1
192.168.160.201 swarm-node2
192.168.160.202 swarm-node3
192.168.160.203 swarm-node4
```

Deploy swarm

```
ansible-playbook -i inventory -u teligent deploy-swarm.yml
```

Перезагрузка всех узлов:
```sh
ansible all -i inventory -u teligent --become -a "/sbin/reboot"
```


Проверка доступности узлов:
```sh
ansible all -i inventory -u teligent --become -m ping
```

Leave all nodes from swarm:
```sh
ansible-playbook -i inventory -u teligent leave-swarm.yml
```