# Workshop Exercise 5.1 - Updating the Image for Deploying a Containerized Application

## Table of Contents

* [Objective](#objective)
* [Step 1 - Reviewing the Requirements for the Application](#step-1---reviewing-the-requirements-for-the-application)
* [Step 2 - Automated Device Update](#step-2---automated-device-update)

## Objective

In this exercise, we'll review creating a new image via automation to host our now containerized application.

For a reminder on the application we're deploying, review [exercise 1.5](../1.5-application-intro).

### Step 1 - Reviewing the Requirements for the Application

Because we've moving to a containerized deployment for our application, we actually will be removing packages from the image. In addition, podman is **always** included in edge images by Image Builder, however here we've explicitly called it out for clarity.

Also included are buildah and skopeo just to show that edge devices can be leveraged to build applications should local atonomy be desired, however in a production deployment it's recommended to build container images on OpenShift using proper CI/CD tooling, then deploy them out to edge devices.

In the interest of time, this has been done for you and will be made available by the instructor. This image was composed using the [infra.osbuild](https://github.com/redhat-cop/infra.osbuild) Ansible collection, which takes a common set of variables and completely automates interactions with Image Builder.

Specifically, this image was customized with the following variables:
```
  - version: 3.0.0
    type: edge-commit
    packages:
      - vim-enhanced
      - git
      - nano
      - podman
      - buildah
      - skopeo
      - NetworkManager-wifi
      - ansible-core
```

### Step 2 - Automated Device Update

Proceed to [this exercise](../0.1-update-rhde/) for next steps on how to get your device updated to the correct image version.

---
**Navigation**

[Previous Exercise](../4.5-cleanup-bare-metal-app) | [Next Exercise](../0.1-upgrade-rhde)

[Click here to return to the Workshop Homepage](../README.md)