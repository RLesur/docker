FROM rocker/verse:3.5.0

RUN apt-get update \
  && apt-get install -y \
  bzip2 \
  lbzip2 \
  curl \
  gnupg \
  gnupg2 \
  gnupg1 \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/

RUN install2.r --error --deps TRUE \
    xaringan \
  && rm -rf /tmp/downloaded_packages/ /tmp/*.rds \
  && Rscript -e "devtools::install_github('wch/webshot');webshot::install_phantomjs()"

RUN mkdir /home/rstudio/bin \
  && cp /root/bin/phantomjs /home/rstudio/bin/
