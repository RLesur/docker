FROM rocker/verse:latest

RUN install2.r --error --deps TRUE \
    blogdown \
    && Rscript -e "blogdown::install_hugo()"

