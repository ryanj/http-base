# http-base [![Build Status](http://img.shields.io/jenkins/s/https/build-shifter.rhcloud.com/http-build.svg)](https://build-shifter.rhcloud.com/job/http-build/) [![Dependency Check](http://img.shields.io/david/ryanj/http-base.svg)](https://david-dm.org/ryanj/http-base)
*A basic HTTP example repo for nodejs, inspired by Raynos/http-framework*

# Local Development
Install dependencies:

```bash
npm install
```

Start a local server:

```bash
npm start
```

# OpenShift V3 / Kubernetes

You'll need the `oc` command line tool to install this project in a Docker-based OpenShift environment.  The cli tool binary is available via the [`openshift/origin` releases page](https://github.com/openshift/origin/releases/).

Use [vagrant](http://openshift.org/vm) or [ansible](https://github.com/openshift/openshift-ansible) to setup your own deployment of OpenShift, then use `oc login` to authenticate. These instructions assume that a basic [nodejs builder image](https://github.com/openshift/origin/tree/master/examples/image-streams) has already been made available in the `openshift` project by an admin.

Build and deploy the application from the command line using the `oc` command line tool, and a nodejs builder image:

    oc new-app openshift/nodejs~https://github.com/ryanj/http-base

After your deployment has completed, find the pod NAME for your hosted container:

    oc get pods

Push changes from a local repo into this environment using the pod NAME from the previous step, allowing you to test your changes without stopping to make a commit:

    oc rsync --exclude='node_modules*' . YOUR_PODNAME:

Use gulp to automatically publish updates your remotely-hosted container as you work:

    PODNAME=YOUR_PODNAME gulp

The included [`gulpfile`](https://github.com/ryanj/http-base/blob/master/gulpfile.js) example will automatically distribute changes from your local `index.html` file into the identified pod.

# License
This code is dedicated to the public domain to the maximum extent permitted by applicable law, pursuant to CC0 (http://creativecommons.org/publicdomain/zero/1.0/)
