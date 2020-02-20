# Dump a table to a local file

First, get the credentials:

```
heroku pg:credentials:url [DATABASE] -a [app_name]
```

Then run `pg_dump`:

```
pg_dump --no-acl --no-owner -h [host ip].compute-1.amazonaws.com -U [user name] -t [table name] --data-only [database name] > table.dump
```

From https://stackoverflow.com/a/16151503
