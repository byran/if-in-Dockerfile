# Building

Both of these examples use a build argument (```BUILDTYPE```) to change what
ends up in the final image.

The default is set to ```linux``` and the linux image can be built using either

```bash
# Implicit specification of the build type using the default in the Dockerfile
$ docker build -t hello-world .
```

```bash
# Explicit specification of the build type
$ docker build -t hello-world --build-arg BUILDTYPE=windows .
```

# If methods

## ```sh if``` method

The ```sh-if/Dockerfile``` allows switching using an ```sh``` if statement on the
```BUILDTYPE``` docker build argument.

This method does appear in the final image and will be messy if used on multiple
```RUN``` instructions.

## Switching ```from``` image method

The ```image-switch/Dockerfile``` allows switching of the final images base (```from```) image.

This method does not appear in the final image and will be cleaner if you want
to optionally run multiple Dockerfile instructions.

It will build all of the possible images, only using the relevant one in the
final image. However if one of the possible images fails to build the entire
build will fail.