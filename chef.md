## Chef

`package`'s  `action :upgrade` always installs the latest available version, even if you specify an earlier version

```
package #{package_name} do
  version #{package_version}
  action :upgrade
end
```

If you want to install a specific version, use `action :install` instead.

https://docs.chef.io/resource_package.html
