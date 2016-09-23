# boinc-server-docker (with drupal)

## Requirements

Same as regular boinc-server-docker, i.e. Docker and docker-compose. 

## Instructions

* clone this repo on the `drupal` branch 
 ```
 git clone --recursive https://github.com/marius311/boinc-server-docker.git drupal
 ```

* bring up the server (the build will take a while the first time)
 ```
 docker-compose up -d --build
 ```

* point browser to localhost/install.php

    *if when you access this page you see an error about the database, wait a few seconds then refresh, it take a moment for the mysql container to boot up*

* click on "Install" and go through the install process

* then do remaining configuration with
```
docker-compose exec apache bash
cd /var/www/html/sites/
drush en boincuser
drush vset boinc_root_dir /root/boinc
```

* point browser to http://localhost/admin/boinc/scheduler and set scheduler URL

* other stuff...
