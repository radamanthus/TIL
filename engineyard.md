# EngineYard-specific snippets

## Check Unicorn queue

This is from @jimneath

```
stats=$(ps aux | egrep -c 'unicor[n].*worker'); stats+=$(awk '/unicorn_[^\.]+.sock/{if($4=="00000000"){if($6=="02"){q+=1};if($6=="03"){a+=1}}};END{print " " a " " q}' t= a=0 q=0 /proc/net/unix); [[ "${stats}" ]] && echo "${stats}" | awk '{printf "%s of %s active, %s requests queued\n", $2, $1, $3}'
```
