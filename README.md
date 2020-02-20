# alpine-openjdk-builds

Alpine OpenJDK builds catalogue for reference and testing purposes.

Builds are either based on the [`openjdk*`][1] apk packages or the respective [OpenJDK Dockerhub][2] image, and consist of a zipped `/usr/lib/jvm/java-<VER>-openjdk` folder.

Zipped debug symbols are based on the [`openjdk*-dbg`][3] apk packages.

### Why not use Alpine repositories?

Alpine repositories only provide the latest version of each package. When a package is upgraded, its historic versions are lost (in some cases, old package versions could still be obtained from earlier Alpine versions). For applications depdending on certain package versions, such as specific OpenJDK 8 builds, this poses a challenge, since package versions could change without notice. In addition, the availability of different builds is important for testing purposes.

This repository keeps Alpine OpenJDK Java builds in the form of zip files, with identical content to the respective openjdk packages. Notably, the OpenJDK debug symbol packages are available as well, to allow low level JVM debugging for each Java build.

### Docker image

All `openjdk8` builds are also available in a consolidated docker image:

`docker run -it shaharv/alpine-java-8-builds`

[1]: https://pkgs.alpinelinux.org/package/v3.8/community/x86/openjdk8
[2]: https://hub.docker.com/_/openjdk
[3]: https://pkgs.alpinelinux.org/package/v3.8/community/x86/openjdk8-dbg
