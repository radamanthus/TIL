# Install issues

Sometimes `npm install` fails during deployment due to network issues. It could be related to the problem reported here: http://stackoverflow.com/questions/18419144/npm-not-working-read-econnreset

Try this workaround:

```
npm cache clean
npm config set registry http://registry.npmjs.org/
```
