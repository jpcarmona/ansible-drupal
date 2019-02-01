# ansible-drupal

* Añadimos box de Debian:

```
vagrant box add debian/stretch64
```

Utilizaremos una interfaz interna "vboxnet" como red de solo-anfitrión en las máquinas.

* Creamos entorno virtual Python3:

```
python3 -m venv ~/entornos/ansible
source ~/entornos/ansible/bin/activate
pip install -r requeriments.txt
```

* Iniciamos vagrant:
```
vagrant up
```
