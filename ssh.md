## Copying files between environments on EY Cloud

This task is usually done when copying a DB dump from an old environment into a new one.

By default the deploy user on one environment is not allowed to ssh to the other environments. To copy files between environments, please add the '-A' parameter when you ssh to the first instance. This way your ssh credentials will be passed on to the next host.

```
ssh -A deploy@<ec2-hostname-of-old-db_master>
```

After logging in to <old-db_master> you should be able to copy files to the db_master of the new environment using scp:

```
scp -v <path-to-dump-file> deploy@<internal-ip-of-new-db_master>:<path-to-db-dump> 
```

## Save your ssh password to the OSX keychain so you don't have to type it every time

Edit (or create) `~/.ssh/config` and add `UseKeychain yes` to the `Host *` block:

```
Host *
    UseKeychain yes
```

https://superuser.com/a/1158050
