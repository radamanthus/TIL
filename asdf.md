# asdf

## PostgreSQL

Installing `PostgreSQL` from `asdf` allows running multiple version of PostgreSQL on the same system.

It's also easy to create a PG data directory for each Rails application.

Create a PG data directory inside the Rails application:

```
cd <railsapp>
initdb -D ./data
```
The current user will be the superuser by default. No password needed.

Start `PostgreSQL` installed from `asdf`

```
/home/rad/.asdf/installs/postgres/14.6/bin/pg_ctl -D ./data -l logfile start
```
