## Delete files that match a pattern

If you're dealing with way too many files you'll get an "Argument list too long" error.

This will delete files in the current directory that match the pattern "*.sess", and is older than 100 days.

```
find . -name "*.sess" -mtime +100 
```

From https://stackoverflow.com/a/27265081

## Get inode usage for the current directory

```
echo "Detailed Inode usage for: $(pwd)" ; for d infind -maxdepth 1 -type d |cut -d\/ -f2 |grep -xv . |sort; do c=$(find $d |wc -l) ; printf "$c\t\t- $d\n" ; done ; printf "Total: \t\t$(find $(pwd) | wc -l)\n"
```

From http://unix.stackexchange.com/a/193188

## Get the process details, given the PID

```
ps -fwwp <PID>
```
