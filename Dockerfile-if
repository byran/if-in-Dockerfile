ARG BUILDTYPE=linux

FROM ubuntu

RUN if test "x${BUILDTYPE}" = "xlinux" ; \
    then \
        echo "Linux" ; \
    else \
        echo "Windows" ; \
    fi
