FROM rocker/verse:3.6.0

RUN apt-get update -qq && apt-get -y --no-install-recommends install \
  libssl-dev \
  && apt-get -y install chromium

RUN apt-get autoremove -y \
  && apt-get autoclean -y \
  && rm -rf /var/lib/apt/lists/*

RUN install2.r pagedown
