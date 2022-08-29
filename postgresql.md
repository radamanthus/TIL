# PostgreSQL

## Start PostgreSQL

On OS X, if PostgreSQL was installed using brew:

`pg_ctl -D /usr/local/var/postgres start`

## Export a query to CSV

Figure out the SQL for the query, then use the `COPY` command:

`COPY (<query here>) TO '<path_to_output_filename>' WITH csv`

Example:

`COPY (SELECT * FROM users) TO '/home/rad/users.csv' WITH csv`
