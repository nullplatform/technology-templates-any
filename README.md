# Nullplatform "Any Technology" Template

This is a minimalistic sample on how you can create an application on arbitrary technology.

In particular, we're spinning up an image that contains an echo server built on top on Nginx.

## How do I modify this template to build my own application?

1. Change the Dockerfile to run the application / binary that you are building
2. Deploy your application in nullplatform

----

**What follows is the original documentation for this docker image**

----

## Nginx Template

### What is this template for ?

This template is designed to streamline the creation of an internal traffic management layer, thereby simplifying the routing of traffic.

### How to use it ?

#### config/rules.conf

This file contains all the rules for managing your traffic. If you intend to direct a specific path to a particular pool, please consider adding something similar to the following example:
```nginx
  location ~ ^/my_path {
      proxy_pass https://my_scope_url;
  }
```

#### config/nginx.conf.tpl

This file contains the primary configuration of the nginx server. Upon instance startup, it will be copied as nginx.conf, and a series of replacements will take place. If you wish to include additional replacements, kindly add them to the `entrypoint.sh` file.
