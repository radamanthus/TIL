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
