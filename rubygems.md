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

## Installing pg gem fails on M1 Mac

Installing the `pg` gem fails to build the native extensions.

Install the PostgreSQL libraries first, then tell bundler where to find them.

```
brew install libpq
bundle config set --global build.pg --with-pg-config=/opt/homebrew/opt/libpq/bin/pg_config
```

`bundle install` should work normally after this.

From https://www.mendelowski.com/docs/ruby/installing-pg-gem-with-bundler-on-mac-m1/
