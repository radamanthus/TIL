## Crontab format

```
# ┌───────────── minute (0 - 59)
# │ ┌───────────── hour (0 - 23)
# │ │ ┌───────────── day of the month (1 - 31)
# │ │ │ ┌───────────── month (1 - 12)
# │ │ │ │ ┌───────────── day of the week (0 - 6) (Sunday to Saturday;
# │ │ │ │ │                                   7 is also Sunday on some systems)
# │ │ │ │ │
# │ │ │ │ │
# * * * * * command to execute
```

https://en.wikipedia.org/wiki/Cron

## Create a swap file

```
sudo dd if=/dev/zero of=/mnt/4GB.swap bs=1024 count=4194304
sudo mkswap /mnt/4GB.swap
sudo swapon /mnt/4GB.swap
sudo chmod 0600 /mnt/4GB.swap
```

Add this line to `/etc/fstab`:

```
/mnt/4GB.swap  none  swap  sw 0  0
```

Add this line to `/etc/sysctl.conf`:

```
vm.swappiness=10
```

Verify that the swap file is in use:

```
sudo swapon -s
```

From https://support.rackspace.com/how-to/create-a-linux-swap-file/

## Delete files that match a pattern

If you're dealing with way too many files you'll get an "Argument list too long" error.

This will delete files in the current directory that match the pattern "*.sess", and is older than 100 days.

```
find . -name "*.sess" -mtime +100 -delete
```

From https://stackoverflow.com/a/27265081

## Generate CPU Load

This Linux pipeline forces the CPU to work on compressing a continuous stream of random data:

```
dd if=/dev/urandom | gzip -9 >> /dev/null &
```

This is useful if you're testing your CPU alerting system.

## Get the environment that cron runs in

Add this to your cron:

```
* * * * * env > ~/cronenv
```

After it runs, do this:

```
env - `cat ~/cronenv` /bin/sh
```

This assumes that your cron runs /bin/sh, which is the default regardless of the user's default shell.

From https://stackoverflow.com/a/2546509

## Get inode usage for the current directory

```
echo "Detailed Inode usage for: $(pwd)" ; for d in `find -maxdepth 1 -type d |cut -d\/ -f2 |grep -xv . |sort`; do c=$(find $d |wc -l) ; printf "$c\t\t- $d\n" ; done ; printf "Total: \t\t$(find $(pwd) | wc -l)\n"
```

From http://unix.stackexchange.com/a/193188

## Get the process details, given the PID

```
ps -fwwp <PID>
```

## Get the Ubuntu version from the command line

```
lsb_release -a
```
