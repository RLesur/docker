FROM rocker/verse:3.5.0

RUN apt-get update \
  && apt-get install -y --no-install-recommends \
  bzip2 \
  lbzip2 \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/

RUN install2.r --error --deps TRUE \
    xaringan \
    webshot \
  && rm -rf /tmp/downloaded_packages/ /tmp/*.rds \
  && Rscript -e "webshot::install_phantomjs()"

RUN mkdir /home/rstudio/bin \
  && cp /root/bin/phantomjs /home/rstudio/bin/
