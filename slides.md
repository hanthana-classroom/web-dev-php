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
