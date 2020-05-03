
# Ansible con Centos 7

Se listan los siguientes archivos:
1. 

## Instalar ansible
```
sudo yum -y install epel-release
sudo yum -y install ansible
```

### Ping ad-hoc al servidor nodo01
```
ansible -i hosts node01 -m ping -k
```

### Conectarse mediante ssh a un nodo01 por ip
#### Generacion de key pub
```
ssh-keygen
```
#### Copiamos nuestro pub en el servidor nodo01
```
ssh-copy-id -i ~/.ssh/id_rsa.pub root@192.168.1.45
```

#### Ping ad-hoc al servidor nodo01 con la contraseña del certificado pub
```
ansible -i hosts node01 -m ping
```

### Ejecutar el playbook en todos los nodos
```
ansible-playbook -i hosts  install_docker.yml.
```
