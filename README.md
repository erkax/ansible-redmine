Role Name
=========

A dirty role to setup and configure redmine! Still a lot of improvement required

Requirements
------------

This role is designed to run on CentOS and needs apache, rvm and at least one
version of ruby installed.


Role Variables
--------------
```
redmine_rails_env:
    RAILS_ENV: 'production'
```

```redmine_app_dir: "/opt/redmine"```

```redmine_user: "redmine"```

```redmine_group: "redmine"```

```redmine_version: "3.3.0"```


Dependencies
------------

This role is designed to install and configure redmine with apache httpd and
mariadb on CentOS. So you will need to setup apache and MariaDB yourself, it's
probably a good idea to check what geerlingguy (this guy is awesome) can do for
you. In my case I use the following roles to install all the required components

  - geerlingguy.apache
  - geerlingguy.mysql
  - rvm_io.rvm1-ruby

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

  - hosts: infra-tools
    become: true
    become_user: root
    roles:
      - { role: geerlingguy.mysql}
      - { role: rvm_io.rvm1-ruby, tags: ruby}
      - { role: geerlingguy.apache }
      - { role: unamur.redmine}

License
-------

BSD

Author Information
------------------

Let me know if you use this role or need more info about how to use it :)
