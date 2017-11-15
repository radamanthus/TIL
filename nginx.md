# Redirect non-https requests to https

For Nginx behind ELB, you need to check http_x_forwarded_proto, otherwise you get an infinite redirect

```
if ($http_x_forwarded_proto != 'https') {
  rewrite ^ https://$host$request_uri? permanent;
}
```
