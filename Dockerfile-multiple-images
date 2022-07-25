ARG BUILDTYPE=linux

FROM ubuntu as base
RUN echo "In both images" > /message.txt

FROM base as linux-image
RUN echo "Linux build" >> /message.txt

FROM base as windows-image
RUN echo "Windows build" >> /message.txt

FROM ${BUILDTYPE}-image
RUN cat /message.txt
