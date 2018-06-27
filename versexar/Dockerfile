FROM rocker/verse:3.5.0

RUN apt-get update \
  && apt-get install -y \
  bzip2 \
  lbzip2 \
  curl \
  gnupg \
  gnupg2 \
  gnupg1 \
  fonts-droid \
  font-droid-fallback \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/

RUN install2.r --error --deps TRUE \
    xaringan \
  && rm -rf /tmp/downloaded_packages/ /tmp/*.rds \
  && Rscript -e "devtools::install_github('wch/webshot');webshot::install_phantomjs()"

RUN mkdir /home/rstudio/bin \
  && cp /root/bin/phantomjs /home/rstudio/bin/

RUN mkdir -p /usr/share/fonts/truetype/yanonekaffeesatz \
  && wget -O /usr/share/fonts/truetype/yanonekaffeesatz/YanoneKaffeesatz-ExtraLight.ttf "https://github.com/google/fonts/blob/master/ofl/yanonekaffeesatz/YanoneKaffeesatz-ExtraLight.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/yanonekaffeesatz/YanoneKaffeesatz-Light.ttf "https://github.com/google/fonts/blob/master/ofl/yanonekaffeesatz/YanoneKaffeesatz-Light.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/yanonekaffeesatz/YanoneKaffeesatz-Regular.ttf "https://github.com/google/fonts/blob/master/ofl/yanonekaffeesatz/YanoneKaffeesatz-Regular.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/yanonekaffeesatz/YanoneKaffeesatz-Bold.ttf "https://github.com/google/fonts/blob/master/ofl/yanonekaffeesatz/YanoneKaffeesatz-Bold.ttf?raw=true"

  
