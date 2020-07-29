
If you are facing *SQLSTATE[HY000] [2002]* issue
```
Change these 2 files 

config.sample.inc.php
libraries/config.default.php
Change with 127.0.0.1
$cfg['Servers'][$i]['host'] = '127.0.0.1';


```
