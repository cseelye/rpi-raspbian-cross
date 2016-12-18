# rpi-raspbian-cross

This is a fork of https://github.com/TGOlson/rpi-raspbian-cross with the baseimage set to a known working rasbian image.

Original README follows:

`rpi-raspbian` base image configured for cross-compilation. This images enables generic building on CI platforms (such as docker hub). `armv7hf-debian-qemu` cross-compilation tools from https://github.com/resin-io-projects/armv7hf-debian-qemu.

This cross-compilation ability is important because building with the qemu ARM emulator can be very slow. The ability to build ARM-based images in CI can reduce time spent waiting and improve build times.

Example:

```
FROM cseelye/rpi-raspbian-cross

RUN ["cross-build-start"]
RUN <commands inside of ARM image>
RUN ["cross-build-end"]
```

References:
  * https://github.com/resin-io-projects/armv7hf-debian-qemu
  * https://resin.io/blog/building-arm-containers-on-any-x86-machine-even-dockerhub/
