FROM rocker/verse:3.5.0

RUN apt-get update \
  && apt-get install -y \
  bzip2 \
  lbzip2 \
  curl \
  gnupg \
  gnupg2 \
  gnupg1 \
  fonts-droid-fallback \
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

RUN mkdir -p /usr/share/fonts/truetype/sourcecodepro \
  && wget -O /usr/share/fonts/truetype/sourcecodepro/SourceCodePro-Black.ttf "https://github.com/google/fonts/blob/master/ofl/sourcecodepro/SourceCodePro-Black.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/sourcecodepro/SourceCodePro-Bold.ttf "https://github.com/google/fonts/blob/master/ofl/sourcecodepro/SourceCodePro-Bold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/sourcecodepro/SourceCodePro-ExtraLight.ttf "https://github.com/google/fonts/blob/master/ofl/sourcecodepro/SourceCodePro-ExtraLight.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/sourcecodepro/SourceCodePro-Light.ttf "https://github.com/google/fonts/blob/master/ofl/sourcecodepro/SourceCodePro-Light.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/sourcecodepro/SourceCodePro-Medium.ttf "https://github.com/google/fonts/blob/master/ofl/sourcecodepro/SourceCodePro-Medium.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/sourcecodepro/SourceCodePro-Regular.ttf "https://github.com/google/fonts/blob/master/ofl/sourcecodepro/SourceCodePro-Regular.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/sourcecodepro/SourceCodePro-Semibold.ttf "https://github.com/google/fonts/raw/18b5208c2a778d85c1312ec3b18b1d3b822cc51a/ofl/sourcecodepro/SourceCodePro-Semibold.ttf"
  
