## Rubygems update error

While upgrading an older version of rubygems you might encounter this error:

```
ERROR:  While executing gem ... (TypeError)
    no implicit conversion of nil into String
```

This is a Rubygems bug: https://github.com/rubygems/rubygems/issues/1560

To fix, you need to delete the `update_rubygems` binary first, then upgrade rubygems:

```
rm /usr/local/bin/update_rubygems
gem update -N --system 2.6.4
```
