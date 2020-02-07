# Apache Mac Setup

1. Navigate to folder and update file httpd.conf 
```
/private/etc/apache2/httpd.conf
```

2. Enable php by uncommenting below line.
```
#LoadModule php7_module libexec/apache2/libphp7.so
```

3. To change the directory update the below.
```
DocumentRoot "/path/anydir"
<Directory "/path/anydir">
    #
    # Possible values for the Options directive are "None", "All",
    # or any combination of:
    #   Indexes Includes FollowSymLinks SymLinksifOwnerMatch ExecCGI MultiViews
    #
    # Note that "MultiViews" must be named *explicitly* --- "Options All"
    # doesn't give it to you.
    #
    # The Options directive is both complicated and important.  Please see
    # http://httpd.apache.org/docs/2.4/mod/core.html#options
    # for more information.
    #
    Options FollowSymLinks Multiviews
    MultiviewsMatch Any

    #
    # AllowOverride controls what directives may be placed in .htaccess files.
    # It can be "All", "None", or any combination of the keywords:
    #   AllowOverride FileInfo AuthConfig Limit
    #
    AllowOverride None

    #
    # Controls who can get stuff from this server.
    #
    Require all granted
</Directory>
```

3. Directory Listing Enable(Optional)
```
<Directory "/path">
    Options Indexes FollowSymLinks Multiviews
    MultiviewsMatch Any
    AllowOverride None
    Require all granted
</Directory>
```

4. Changing Php permission to create files with logged in user privilage
```
Find below and change 
From
User _www
Group _www
To
User your_mac_username
Group staff
Note : Our primary group is always staff unless you or your user directory manager changed it.
> sudo apachectl restart
```

5. Change permission of that directory(Optional)
```
chmod -R 777 /path/anydir
```

6. Changing max upload size, Run below command
```
sudo cp /etc/php.ini.default /etc/php.ini
then modify php.ini
upload_max_filesize = 0
post_max_size = 0
```

7. Add to vhosts(Optional)
```
/private/etc/apache2/extra/httpd-vhosts.conf
<Directory "/path/anydir">
    Options Indexes FollowSymLinks MultiViews
    AllowOverride None
    Order allow,deny
    Allow from all
</Directory>
```
