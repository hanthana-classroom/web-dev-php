# IMPORTANT FILES AND LOCATIONS

  1. Apache configuration

    Most Redhat base distributions:

    Main file: /etc/httpd/conf/httpd.conf

        /etc/httpd/
        ├── conf
        ├── conf.d
        ├── conf.modules.d
        ├── logs -> ../../var/log/httpd
        ├── modules -> ../../usr/lib/httpd/modules
        └── run -> /run/httpd

    Most Debian based distributions:

    Main file: /etc/apache2/apache2.conf

        /etc/apache2/
        ├── conf.d
        ├── mods-available
        ├── mods-enabled
        └── sites-available

# IMPORTANT FILES AND LOCATIONS (Cont.)

  2. PHP

    Most Redhat base distributions:

    Main file: /etc/[php]/php.ini

        /etc/[php]
        ├── conf.d
        └── php.ini

    Most Debian based distributions:

    Main file: /etc/php5/apache2/php.ini

        /etc/php5/
        ├── apache2
        │   └── conf.d -> ../conf.d
        ├── cli
        │   └── conf.d -> ../conf.d
        ├── conf.d
        └── mods-available

# DEVELOPMENT ENVIRONMENT

  * Find out which user Apache run as (usually http or www-data).
  * Let Apache read files in our $HOME directory.

        sudo gpasswd http `id -gn`
        chmod g+rX $HOME

  * Create a configuration file somewhere in the user home directory and include
    (or symlink) it into the Apache configuration.

    >     LoadModule php5_module modules/libphp5.so
    >     AddHandler application/x-httpd-php .php
    >
    >     <VirtualHost 127.0.0.1:80>
    >         ServerName name_that_resolve_to_above_ip
    >
    >         DocumentRoot /home/YOUR_USERNAME/path/to/project
    >         DirectoryIndex index.php
    >
    >         <Directory />
    >             Require ip 127.0.0.1
    >         </Directory>
    >
    >     </VirtualHost>

      Note: It would be useful to make Apache load multiple configuration files
      from a directory with your home directory when working on several projects
      at the same time.