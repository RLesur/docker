FROM rocker/verse:3.5.0

RUN install2.r --error --deps TRUE \
    xaringan \
    webshot \
  && rm -rf /tmp/downloaded_packages/ /tmp/*.rds \
  && Rscript -e "webshot::install_phantomjs()"
