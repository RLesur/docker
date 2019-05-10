FROM r-base:3.6.0

RUN apt-get update \
    && apt-get install -y libcurl4-openssl-dev \
    && rm -rf /var/lib/apt/lists/*

RUN install.r remotes \
    && installGithub.r -d TRUE ropenscilabs/tic
