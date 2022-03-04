# # user database

## sqlite (preferred)
in the spirit of minimalism, the recommended database technology to use here is sqlite. sqlite databases exist as a single, atomic file, and are a good use for light applications, with low to medium concurrent loads.<br>
it also allows for greater flexibility, and segregation for your application's data: you can create as many sqlite databases as you need.

- [documentation](https://sqlite.org/docs.html)
- [sqlite cli](https://sqlite.org/cli.html)

## optional

please contact <a href="https://envs.net/~creme/">creme</a> (via matrix or email) to request a database with access.

### mysql

- [documentation](https://dev.mysql.com/doc/mysql-getting-started/en/)

on `localhost` port `3306`

- database name: `username`
- database user: `username`
- password: *please see in your database readme email*

*do not store password change to history:*<br />
&nbsp;&nbsp;*`export MYSQL_HISTFILE=/dev/null`*

connecting to mysql:<br />
&nbsp;&nbsp;`mysql -u username -p`

change your password:<br />
&nbsp;&nbsp;`SET PASSWORD = PASSWORD('your-password-here');`

use database:<br />
&nbsp;&nbsp;`use username`

#### database backup & restore
simple backup:<br />
&nbsp;&nbsp;`mysqldump "$USER" -p > ~/backup/dump_"$USER".sql`

and restore:<br />
&nbsp;&nbsp;`mysql -p -u "$USER" < ~/backup/dump_"$USER".sql`

you can also use our `envs_mysql.sh` - backup and restore script.<br />
the backup files will stored under `~/backup/`.

show `envs_mysql.sh -h` for more informations
```bash
usage: envs_mysql.sh
			backup				- backup your default user database
			backup <db_name>	- backup database
			restore				- restore your latest user database
			restore <db_name>	- restore database
```

with cron you can also do your backup regularly at a certain time.<br />
see [help -&gt; cron](https://help.envs.net/help/#croncrontab) for a example.
