Discourse with Docker
========

Setup Discourse on your server using Docker

Installation
--------------

`ansible-galaxy install alekseenkoss77.discourse`

Role Variables
--------------
`defaults/main.yml`

```yml
discourse_app:
  user: web
  root_path: '/var/discourse'
  default_locale: en
  lang: en_US.UTF-8
  unicorn_workers: 3
  cdn_url: '//discourse-cdn.example.com'
  git_revision: tests-passed
  hostname: 'discourse.example.com'
  admins:
    - admin@example.com
  db:
    search_conf: "pg_catalog.english"
    db_shared_buffers: 256MB
    db_work_mem: 40MB
  smtp:
    address: smtp.example.com
    port: 587
    user: 'user@example.com'
    pass: 'pa$$word'
    tls: true
```

Example Playbook
-------------------------
```yml
  - hosts: servers
    roles:
       - alekseenkoss77.discourse
```
