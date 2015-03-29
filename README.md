# ansible-role.php_fpm

Install
========
```
git submodule add git@github.com:Waldz/php_fpm.nginx.git roles/php_fpm
```

Example
========
```
- name: Install PHP to all servers
  hosts: all
  sudo: true
  vars_files:
    - vars/defaults/php.yml
  roles:
    #- role: nginx
    - role: php_fpm
  tags: [php]
```

Variables
========
vars/defaults/php.yml
```
---
php_extensions:
  - php5-mysql
  - php5-mcrypt

php_config:
  - option: display_errors
    value: Off
  - option: error_reporting
    value: "E_ALL & ~E_DEPRECATED & ~E_STRICT"
  - option: error_log
    value: "{{ php_path_log }}/php-errors.log"
  - option: short_open_tag
    value: "On"
```
