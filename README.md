
# Ansible con Centos 7

<img src="https://www.ansible.com/hubfs/2016_Images/Blog_Headers/Ansible-Docker-Blog-2.png"></a>

## Instalar docker con ansible

### Archivos principales del repo:
1. Ansible.pptx : Presentacion de Ansible.
2. ansible.cfg : Archivo con las configuraciones por defecto de ansible.
3. hosts : Archivo con la lista de los nodos agrupados y con parametro por defecto para establecer la conexion a los nodos.
4. install_docker.yml : archivo playbook con los taks para la instalacion de docker.

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
#### Copiamos nuestro pub en el servidor nodo01 y nodo02
```
ssh-copy-id -i ~/.ssh/id_rsa.pub root@192.168.1.45
ssh-copy-id -i ~/.ssh/id_rsa.pub root@192.168.1.39
```

#### Ping ad-hoc al servidor nodo01 con la contraseña del certificado pub
```
ansible -i hosts node01 -m ping
```

### Ejecutar el playbook en todos los nodos
```
ansible-playbook -i hosts  install_docker.yml.
```
