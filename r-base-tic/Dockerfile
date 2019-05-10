FROM r-base:3.6.0

RUN  apt-get update \
  && apt-get install -y --no-install-recommends \
       libcurl4-openssl-dev \
       libssl-dev \
       libgit2-dev \
       file \
  && rm -rf /var/lib/apt/lists/*

RUN  install.r remotes \
  && installGithub.r ropenscilabs/tic \
  && rm -rf /tmp/downloaded_packages/ /tmp/*.rds
