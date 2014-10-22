mtvb/zonify
============

use [AirBNB Zonify](https://github.com/airbnb/zonify) to update a route53 managed domain with EC2 instances.

## set AWS configuration

you have to provide at least the following environment variables:
- AWS_ACCESS_KEY
- AWS_SECRET_ACCESS_KEY

you can override the following environment variables
- AWS_REGION (default is eu-west-1)
- EC2_URL (default is ec2.eu-west-1.amazonaws.com)

## ENTRYPOINT & CMD
This dockerfile sets the entrypoint to ```zonify```. 

## Examples

### Display the built-in help

```shell docker run -it mtvb/zonify help```

### Sync your EC2 zone in eu-west-1 to route53

```shell docker run -it -e AWS_ACCESS_KEY=base64... -e AWS_SECRET_ACCESS_KEY=base64.. mtvb/zonify sync example.com name.tag:.```

if your AWS credentials are set in the environment on your workstation, this could also work:

```shell docker run -it -e AWS_ACCESS_KEY=$AWS_ACCESS_KEY -e AWS_SECRET_ACCESS_KEY=$AWS_SECRET_ACCESS_KEY mtvb/zonify sync example.com name.tag:.```

