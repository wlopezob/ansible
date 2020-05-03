
# ansible con Centos 7

## instalar ansible
```
sudo yum -y install epel-release
sudo yum -y install ansible
```

## ping ad-hoc al servidor nodo01
```
ansible -i hosts node01 -m ping -k
```

## conectarse mediante ssh a un nodo01 por ip
### generacion de key pub
```
ssh-keygen
```
### copiamos nuestro pub en el servidor nodo01
```
ssh-copy-id -i ~/.ssh/id_rsa.pub root@192.168.1.45
```

## ping ad-hoc al servidor nodo01 con la contraseña del certificado pub
```
ansible -i hosts node01 -m ping
```
