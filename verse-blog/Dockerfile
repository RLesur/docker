FROM rocker/verse:3.4.1

RUN install2.r --error --deps TRUE \
    blogdown \
    && Rscript -e "blogdown::install_hugo()"

