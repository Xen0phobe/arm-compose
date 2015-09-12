# arm-compose

This is an automated build for docker-compose on ARM.
This build clones the official repo [docker/compose](https://github.com/docker/compose) and generates an ARMv7 binary.

## Customize the build

The only customization is done in the `VERSION` file. This file contains the tag to build.

## Patches

There are some file that have to be patched in the upstream repo. These files are in the `patches` folder.

### Patches for ARM

For the ARM cpu type we have to patch the Dockerfile to adjust the `FROM` line and downloading a docker deb package.

* Dockerfile

### Patches for Drone

We use Drone to do the Build on a Scaleway server. As drone itself runs Docker containers we have to adjust some parts in the dockerindocker build.

* script/build-linux
* script/build-linux-inner
