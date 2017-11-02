FROM rocker/verse:3.4.1

RUN install2.r --error --deps TRUE \
    blogdown \
    plot3D \
    animation \
    && Rscript -e "blogdown::install_hugo()"

