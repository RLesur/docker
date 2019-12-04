FROM rocker/verse:3.6.0

ENV PATH=$PATH:/usr/local/context/tex/texmf-linux/bin:/usr/local/context/bin
ENV OSFONTDIR=/usr/share/fonts
ENV TEXROOT=/usr/local/context/tex

RUN apt-get update -qq && apt-get -y --no-install-recommends install \
  rsync

RUN apt-get autoremove -y \
  && apt-get autoclean -y \
  && rm -rf /var/lib/apt/lists/*

RUN mkdir /usr/local/context \
  && chown -R root:staff /usr/local/context \
  && chmod -R 2775 /usr/local/context \
  && cd /usr/local/context \
  && wget https://minimals.contextgarden.net/setup/first-setup.sh \
  && chmod +x first-setup.sh \
  && ./first-setup.sh \
  && echo "PATH=${PATH}" >> /usr/local/lib/R/etc/Renviron \
  && echo "OSFONTDIR=${OSFONTDIR}" >> /usr/local/lib/R/etc/Renviron \
  && echo "TEXROOT=${TEXROOT}" >> /usr/local/lib/R/etc/Renviron \
  && installGithub.r rlesur/rmarkdown@context_document
