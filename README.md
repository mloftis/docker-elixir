# About this Repo

[![Docker Stars](https://img.shields.io/docker/stars/mloftis/elixir-extended.svg?style=flat-square)](https://hub.docker.com/mloftis/elixir/)
[![Docker Pulls](https://img.shields.io/docker/pulls/mloftis/elixir-extended.svg?style=flat-square)](https://hub.docker.com/mloftis/elixir/)
Latest Build Size ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/mloftis/elixir-extended/latest)


Normal fat image builds now pulling in OpenCL ICD and pocl.  These packages do not appear to exist in alpine (and we've never used alpine anyway) (20190721)

Latest has been moved to 1.15otp26! (20231018)

Stopped building 1.4 through 1.7, 1.8-alpine. (20211010)

Deploying additional build(s) with OTP 22 as the base! (see tags with otp22) 

This image builds off of the elixir image, but only for the "fat" builds.  It adds Pg client and GMP libs.

More things to come as needed for my own use, but, feel free to use this for yours.  I won't be removing anything from the builds only adding to them, check the Dockerfile's to see what
packages get added.  For general use elixir, please use the official images!

