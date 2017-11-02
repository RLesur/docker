FROM rocker/verse:3.4.1

RUN apt-get update \
  && apt-get install -y --no-install-recommends \
  r-cran-rgl \
  mesa-common-dev \
  libglu1-mesa-dev \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/ \
  && rm -rf /tmp/downloaded_packages/ /tmp/*.rds

RUN install2.r --error --deps TRUE \
    blogdown \
    plot3D \
    animation \
  && Rscript -e "blogdown::install_hugo()"

