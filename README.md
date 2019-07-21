# About this Repo

[![Docker Stars](https://img.shields.io/docker/stars/mloftis/elixir-extended.svg?style=flat-square)](https://hub.docker.com/imloftis/elixir/)
[![Docker Pulls](https://img.shields.io/docker/pulls/mloftis/elixir-extended.svg?style=flat-square)](https://hub.docker.com/mloftis/elixir/)
[![](https://images.microbadger.com/badges/commit/mloftis/elixir-extended.svg)](https://microbadger.com/images/mloftis/elixir-extended "Get your own commit badge on microbadger.com")

[![](https://images.microbadger.com/badges/version/mloftis/elixir-extended.svg)](https://microbadger.com/images/mloftis/elixir-extended "Get your own version badge on microbadger.com")[![](https://images.microbadger.com/badges/image/mloftis/elixir-extended.svg)](https://microbadger.com/images/mloftis/elixir-extended "Get your own image badge on microbadger.com")

[![](https://images.microbadger.com/badges/version/mloftis/elixir-extended:1.8otp22.svg)](https://microbadger.com/images/mloftis/elixir-extended:1.8otp22 "Get your own version badge on microbadger.com")[![](https://images.microbadger.com/badges/image/mloftis/elixir-extended:1.8otp22.svg)](https://microbadger.com/images/mloftis/elixir-extended:1.8otp22 "Get your own image badge on microbadger.com")

Normal fat image builds now pulling in OpenCL ICD and pocl.  These packages do not appear to exist in alpine (and we've never used alpine anyway) (20190721)

Latest has been moved from 1.6 to 1.9otp22! (20190715)

Deploying additional build(s) with OTP 22 as the base! (see tags with otp22) 

This image builds off of the elixir image, but only for the "fat" builds.  It adds Pg client and GMP libs.

More things to come as needed for my own use, but, feel free to use this for yours.  I won't be removing anything from the builds only adding to them, check the Dockerfile's to see what
packages get added.  For general use elixir, please use the official images!

