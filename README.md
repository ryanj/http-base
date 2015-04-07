# http-base [![Build Status](http://img.shields.io/jenkins/s/https/build-shifter.rhcloud.com/http-build.svg)](https://build-shifter.rhcloud.com/job/http-build/) [![Dependency Check](http://img.shields.io/david/ryanj/http-base.svg)](https://david-dm.org/ryanj/http-base)
*A basic HTTP example repo for nodejs, inspired by Raynos/http-framework*

[![Launch on OpenShift](https://launch-shifter.rhcloud.com/launch.svg)](https://openshift.redhat.com/app/console/application_type/custom?cartridges%5B%5D=nodejs-0.10&initial_git_url=https%3A%2F%2Fgithub.com%2Fryanj%2Fhttp-base.git&name=httpbase)

To deploy a clone of this application using the [`rhc` command line tool](http://rubygems.org/gems/rhc):

    rhc app create httpbase nodejs-0.10 --from-code=https://github.com/ryanj/http-base.git
    
Or [link to a web-based clone+deploy](https://openshift.redhat.com/app/console/application_type/custom?cartridges%5B%5D=nodejs-0.10&initial_git_url=https%3A%2F%2Fgithub.com%2Fryanj%2Fhttp-base.git) on [OpenShift Online](http://OpenShift.com) or on [your own OpenShift cloud](http://openshift.github.io): 

    https://openshift.redhat.com/app/console/application_type/custom?cartridges%5B%5D=nodejs-0.10&initial_git_url=https%3A%2F%2Fgithub.com%2Fryanj%2Fhttp-base.git

## Local Development
Install dependencies:

```bash
npm install
```

Start a local server:

```bash
npm start
```

## Docker
To run [the related docker image](https://registry.hub.docker.com/u/ryanj/http-base/):

```bash
docker pull ryanj/http-base
docker run -d -p 8080:8080 -e "HOSTNAME=localhost" -e "APP_NAME=app_name" ryanj/http-base
```

## License
This code is dedicated to the public domain to the maximum extent permitted by applicable law, pursuant to CC0 (http://creativecommons.org/publicdomain/zero/1.0/)
