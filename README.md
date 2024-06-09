# Automatización de instalacion de servicios y aplicaciones mediante Ansible
Realizado en entorno *Debian*, con una lista básica de servicios y aplicaciones y contiene ficheros para poder llevar a cabo la monitorización de las automatizaciones con Ansible.

A continuación se pueden ver los servizos y las aplicaciones

| Servizos  | Aplicaciones |
| --- | ---------------------- |
| DNS (bind9) |  |
| DHCP (isc-dhc-server) |  |
| FTP (vsftpd) |   |
| Samba | |
| Apache |  |
| Docker |  |
| DDNS (bind9 + isc-dhcp-server) |  |

# 1.Preparación del entorno
## 1.1 En el equipo central

Para realizar cualquiera acción con Ansible primero hai tanto el propio programa como sus dependencias.

Primero se debe comprobar la versión de python, dado que tiene que ser igual o superior a la 2.6.
```
python3 -V
```

Si es inferior se debe de instalar la nueva versión:
```
apt update
apt install -y python3
```

De último se debe instalar *software-properties-common*:
```
apt install -y software-properties-common
```

Unha vez certificada la versión o/y instalado las dependencias es cuando se realiza la de la herramienta *Ansible*.
```
apt install -y ansible
```

Para comprobar la instalación se ejecutara el siguiente comando:
```
ansible --version
```

Si no se genero ningún archivo de configuración se debe crear el archivo de configuración en la ruta por defecto:
```
mkdir /etc/ansible
touch ansible.cfg
```

Unha vez creado se edita añadiendo la siguiente información que indica cual es el inventario por defecto:
```
[defaults]
inventory=/etc/ansible/hosts
```
Justo después de esto se comprueba con el siguiente comando si ya emplea el archivo de configuración creado.
```
ansible --version
```

## 1.2 En los equipos clientes *Linux*
En los equipos *Linux* lo único que se necesita es la versión *server* del servicio SSH.
```
apt install -y ssh
```

## 1.3 En los equipos clientes *Windows*
En los equipos *Windows* es más ociosa la tarea dadas las acciones que se deben llevar.

Primero se tiene que actualizar Powershell y .NET Framework.
```

```

