## Ruby

Which gems in my Gemfile are using native libraries?

Run this from irb:

```
puts `bundle show --paths`.split("\n").select{ |dep| File.directory?("#{dep}/ext") }.map{ |dep| dep.split('/').last }.join("\n")
```

From: https://devcenter.heroku.com/articles/ruby-segfault