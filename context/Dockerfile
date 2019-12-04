FROM rocker/verse:3.6.0

ENV PATH=$PATH:/usr/local/context/tex/texmf-linux/bin:/usr/local/context/bin
ENV OSFONTDIR=/usr/share/fonts
ENV TEXROOT=/usr/local/context/tex

RUN mkdir /usr/local/context \
  && chown -R root:staff /usr/local/context \
  && chmod -R 2775 /usr/local/context \
  && wget https://minimals.contextgarden.net/setup/first-setup.sh ‐P /usr/local/context \
  && sh /usr/local/contextfirst-setup.sh \
  && echo "PATH=${PATH}" >> /usr/local/lib/R/etc/Renviron \
  && echo "OSFONTDIR=${OSFONTDIR}" >> /usr/local/lib/R/etc/Renviron \
  && echo "TEXROOT=${TEXROOT}" >> /usr/local/lib/R/etc/Renviron \
  && installGithub.r rlesur/rmarkdown@context_document
