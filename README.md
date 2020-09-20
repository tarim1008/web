Role Web
=========

Installer apache et php avec une application web de test.

Requirements
------------

Les familles Debian et RedHat

Role Variables
--------------

| nom                     | type   | description                                                     | obligatoire |
|-------------------------|--------|-----------------------------------------------------------------|-------------|
| `mysql_user`            | string | Mysql user that will be used in the php app                     |   oui       |
| `mysql_password`        | string | Mysql password that will be used in the php app                 |   oui       |
| `mysql_dbname`          | string | Database name that will be used in the php app                  |   oui       |
| `db_host`               | string | Database ip/host that that will be used in the php app          |   oui       |
| `extra_packages_debian` | list   | extra Debian packages that will be downloaded                   |   non       |
| `extra_packages_redhat` | list   | extra RedHat packages that will be downloaded                   |   non       |

Dependencies
------------

n/a

Example Playbook
----------------

```yaml
- hosts: web
  become: yes
  vars: vars/main.yml
    - mysql_user: "admin"
    - mysql_password: "Test_34535$"
    - mysql_dbname: "blog"
    - db_host: "192.168.0.22"
    - extra_packages_debian: ['php-curl', 'php-gd', 'php-mbstring'] 
    - extra_packages_redhat: ['php-xml', 'php-gd', 'php-mbstring'] 

  roles:
    - web
```

License
-------

BSD

Author Information
------------------

Tarim1008
