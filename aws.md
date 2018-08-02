# Console logout

https://console.aws.amazon.com/console/logout!doLogout

# npm install issues

Sometimes `npm install` fails during deployment due to network issues. It could be related to the problem reported here: http://stackoverflow.com/questions/18419144/npm-not-working-read-econnreset

Try this workaround:

```
npm cache clean
npm config set registry http://registry.npmjs.org/
```

# Get AWS instance metadata

To get the public hostname of the EC2 instance you're in:

```
curl http://169.254.169.254/latest/meta-data/public-hostname
```

From http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html

# Resize an AWS EBS volume

http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-expand-volume.html

Resize it on the AWS Console. Then SSH to the instance that the volume is attached to.

Run `df -h` to get the filesystem (/dev/xvdb, /dev/xvdz2, etc.)

```
Filesystem      Size  Used Avail Use% Mounted on
rootfs           15G  4.9G  9.2G  35% /
/dev/root        15G  4.9G  9.2G  35% /
tmpfs           1.9G  196K  1.9G   1% /run
udev             10M     0   10M   0% /dev
shm             1.9G     0  1.9G   0% /dev/shm
cgroup_root      10M     0   10M   0% /sys/fs/cgroup
/dev/xvdb        99G  349M   94G   1% /mnt
/dev/xvdz2       99G   11G   83G  12% /db
```

Extend the filesystem: `sudo resize2fs /dev/xvdz2`

Grow the filesytem: `sudo xfs_growfs -d /db`

Verify the new size by running `df -h` again.
