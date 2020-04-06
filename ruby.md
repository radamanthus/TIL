## Ruby

Which gems in my Gemfile are using native libraries?

Run this from irb:

```
puts `bundle show --paths`.split("\n").select{ |dep| File.directory?("#{dep}/ext") }.map{ |dep| dep.split('/').last }.join("\n")
```

From: https://devcenter.heroku.com/articles/ruby-segfault

## Freeze a string

```
-'my string'
```

More compact than 

```
'my string'.freeze
```

https://bugs.ruby-lang.org/issues/11782

## Read a CSV file from Heroku console

Put the CSV file into a secret gist, then get the URL of the raw file.

```
require 'open-uri'
file = open(url)
csv = CSV.new(file)
lines = csv.readlines
```
