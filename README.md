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


* Estructura Ficheros:

```
├── ansible.cfg
├── group_vars
│   └── all
│       └── vars.yml
├── playbook.yml
└── roles
    ├── apache2
    │   ├── tasks
    │   │   └── main.yml
    │   └── templates
    ├── bind9
    │   └── tasks
    │       └── main.yml
    ├── common
    │   └── tasks
    │       └── main.yml
    ├── drupal
    │   └── tasks
    │       └── main.yml
    └── postgresql
        └── tasks
            └── main.yml
```
