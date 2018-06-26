FROM rocker/verse:3.5.0

RUN apt-get update \
  && apt-get install -y --no-install-recommends \
  bzip2 \
  lbzip2 \
  curl \
  gnupg \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/

RUN install2.r --error --deps TRUE \
    xaringan \
  && rm -rf /tmp/downloaded_packages/ /tmp/*.rds \
  && Rscript -e "devtools::install_github('wch/webshot');webshot::install_phantomjs()"

RUN mkdir /home/rstudio/bin \
  && cp /root/bin/phantomjs /home/rstudio/bin/

RUN curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash - \
  && sudo apt-get install -y nodejs \
  && sudo apt-get install -y build-essential \
  && useradd node \
  && mkdir -p /usr/src/app \
  && chown node:node /usr/src/app \
  && npm install -g decktape
