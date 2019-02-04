# ansible-drupal

* Estructura Ficheros en ansible:

```
ansible/
├── ansible.cfg
├── group_vars
│   └── all
│       └── vars.yml
├── playbook.yml
└── roles
    ├── apache2
    │   ├── handlers
    │   │   └── main.yml
    │   ├── tasks
    │   │   └── main.yml
    │   └── templates
    │       └── drupal.conf.j2
    ├── bind9
    │   ├── handlers
    │   │   └── main.yml
    │   ├── tasks
    │   │   └── main.yml
    │   └── templates
    │       ├── db_zone_ip.j2
    │       ├── db_zone.j2
    │       └── zona.juanpe.j2
    ├── common
    │   └── tasks
    │       └── main.yml
    ├── drupal
    │   └── tasks
    │       └── main.yml
    └── postgresql
        ├── files
        │   └── pg_hba.conf
        ├── handlers
        │   └── main.yml
        ├── tasks
        │   └── main.yml
        ├── templates
        │   └── pg_hba.j2
        └── vars
            └── main.yml
```

## Para creación de escenario

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

* Añadimos el servidor dns al resolv.conf del cliente.

* Entramos en url según tengamos definido en las variables.

