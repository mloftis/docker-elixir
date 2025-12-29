# About this Repo

[![Docker Stars](https://img.shields.io/docker/stars/mloftis/elixir-extended.svg?style=flat-square)](https://hub.docker.com/mloftis/elixir/)
[![Docker Pulls](https://img.shields.io/docker/pulls/mloftis/elixir-extended.svg?style=flat-square)](https://hub.docker.com/mloftis/elixir/)
Latest Build Size ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/mloftis/elixir-extended/latest)


Normal fat image builds now pulling in OpenCL ICD and pocl.  These packages do not appear to exist in alpine (and we've never used alpine anyway) (20190721)

Builds for 1.19 coming up (20251228)
Planning on bumping latest to 1.18 soon.

Latest has been moved to 1.17! (20241126)

Stopped building 1.4 through 1.7, 1.8-alpine. (20211010)

LATEST moved to 1.17 (on OTP 27)

Added 1.18 (on OTP 27) (20250802)

All versions prior to 1.14otp25 REMOVED (20241126)

This image builds off of the elixir image, but only for the "fat" builds.  It adds Pg client and GMP libs.

I kind of lied, I *AM* now removing ancient unsupported images from my builds and tags.  Too many security vulns, and I want to discourage using them.

For general usei of elixir, please use the official images!

