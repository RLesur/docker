FROM rocker/verse:3.5.0

RUN apt-get update \
  && apt-get install -y \
  bzip2 \
  lbzip2 \
  curl \
  gnupg \
  gnupg2 \
  gnupg1 \
  libfontconfig1 \
  fonts-droid-fallback \
  fonts-noto \
  # needed for Chrome:
  fonts-liberation \
  libappindicator3-1 \
  libxss1:amd64 \
  xdg-utils \
  gconf-service \
  libasound2 \
  libatk1.0-0 \
  libc6 \
  libcairo2 \
  libcups2 \
  libdbus-1-3 \
  libexpat1 \
  libfontconfig1 \
  libgcc1 \
  libgconf-2-4 \
  libgdk-pixbuf2.0-0 \
  libglib2.0-0 \
  libgtk-3-0 \
  libnspr4 \
  libpango-1.0-0 \
  libpangocairo-1.0-0 \
  libstdc++6 \
  libx11-6 \
  libx11-xcb1 \
  libxcb1 \
  libxcomposite1 \
  libxcursor1 \
  libxdamage1 \
  libxext6 \
  libxfixes3 \
  libxi6 \
  libxrandr2 \
  libxrender1 \
  libxss1 \
  libxtst6 \
  ca-certificates \
  libappindicator1 \
  libnss3 \
  lsb-release \
  wget \
  x11-apps \
  #xvfb fluxbox x11vnc dbus libasound2 libqt4-dbus libqt4-network libqtcore4 libqtgui4 libxss1 libpython2.7 libqt4-xml libaudio2 libmng1 fontconfig liblcms2-2 liblcms2-dev liblcms2-utils lib32stdc++6 libasound2 lib32ncurses5 libc6-i386 lib32gcc1 nano \
  #python-gobject-2 \
  #curl git \
  chromium chromium-l10n \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/

#RUN apt-get update -qqy \
#  && apt-get -qqy install libnss3 libnss3-tools libfontconfig1 wget ca-certificates apt-transport-https inotify-tools unzip \
#  libpangocairo-1.0-0 libx11-xcb-dev libxcomposite-dev libxcursor1 libxdamage1 libxi6 libgconf-2-4 libxtst6 libcups2-dev \
#  libxss-dev libxrandr-dev libasound2-dev libatk1.0-dev libgtk-3-dev ttf-ancient-fonts chromium-codecs-ffmpeg-extra libappindicator3-1 \
#&& rm -rf /var/lib/apt/lists/* /var/cache/apt/*

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
  && wget -O /usr/share/fonts/truetype/sourcecodepro/SourceCodePro-Black.ttf "https://fonts.gstatic.com/s/sourcecodepro/v7/HI_XiYsKILxRpg3hIP6sJ7fM7PqtvszDs-cv.ttf" \
  && wget -O /usr/share/fonts/truetype/sourcecodepro/SourceCodePro-Bold.ttf "https://fonts.gstatic.com/s/sourcecodepro/v7/HI_XiYsKILxRpg3hIP6sJ7fM7Pqths7Ds-cv.ttf" \
  && wget -O /usr/share/fonts/truetype/sourcecodepro/SourceCodePro-ExtraLight.ttf "https://fonts.gstatic.com/s/sourcecodepro/v7/HI_XiYsKILxRpg3hIP6sJ7fM7Pqt8srDs-cv.ttf" \
  && wget -O /usr/share/fonts/truetype/sourcecodepro/SourceCodePro-Light.ttf "https://fonts.gstatic.com/s/sourcecodepro/v7/HI_XiYsKILxRpg3hIP6sJ7fM7PqtlsnDs-cv.ttf" \
  && wget -O /usr/share/fonts/truetype/sourcecodepro/SourceCodePro-Medium.ttf "https://fonts.gstatic.com/s/sourcecodepro/v7/HI_XiYsKILxRpg3hIP6sJ7fM7PqtzsjDs-cv.ttf" \
  && wget -O /usr/share/fonts/truetype/sourcecodepro/SourceCodePro-Regular.ttf "https://fonts.gstatic.com/s/sourcecodepro/v7/HI_SiYsKILxRpg3hIP6sJ7fM7PqlPevT.ttf" \
  && wget -O /usr/share/fonts/truetype/sourcecodepro/SourceCodePro-Semibold.ttf "https://fonts.gstatic.com/s/sourcecodepro/v7/HI_XiYsKILxRpg3hIP6sJ7fM7Pqt4s_Ds-cv.ttf"
  
RUN mkdir -p /usr/share/fonts/truetype/parisienne \
  && wget -O /usr/share/fonts/truetype/parisienne/Parisienne-Regular.ttf "https://github.com/google/fonts/blob/master/ofl/parisienne/Parisienne-Regular.ttf?raw=true"

RUN mkdir -p /usr/share/fonts/truetype/exo \
  && wget -O /usr/share/fonts/truetype/exo/Exo-Black.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-Black.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-BlackItalic.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-BlackItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-Bold.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-Bold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-BoldItalic.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-BoldItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-ExtraBold.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-ExtraBold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-ExtraBoldItalic.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-ExtraBoldItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-ExtraLight.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-ExtraLight.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-ExtraLightItalic.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-ExtraLightItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-Italic.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-Italic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-Light.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-Light.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-LightItalic.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-LightItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-Medium.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-Medium.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-MediumItalic.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-MediumItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-Regular.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-Regular.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-SemiBold.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-SemiBold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-SemiBoldItalic.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-SemiBoldItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-Thin.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-Thin.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/exo/Exo-ThinItalic.ttf "https://github.com/google/fonts/blob/master/ofl/exo/Exo-ThinItalic.ttf?raw=true"

RUN mkdir -p /usr/share/fonts/truetype/philosopher \
  && wget -O /usr/share/fonts/truetype/philosopher/Philosopher-Bold.ttf "https://github.com/google/fonts/blob/master/ofl/philosopher/Philosopher-Bold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/philosopher/Philosopher-BoldItalic.ttf "https://github.com/google/fonts/blob/master/ofl/philosopher/Philosopher-BoldItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/philosopher/Philosopher-Italic.ttf "https://github.com/google/fonts/blob/master/ofl/philosopher/Philosopher-Italic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/philosopher/Philosopher-Regular.ttf "https://github.com/google/fonts/blob/master/ofl/philosopher/Philosopher-Regular.ttf?raw=true"

RUN mkdir -p /usr/share/fonts/truetype/lato \
  && wget -O /usr/share/fonts/truetype/lato/Lato-Black.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-Black.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-BlackItalic.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-BlackItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-Bold.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-Bold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-BoldItalic.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-BoldItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-ExtraBold.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-ExtraBold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-ExtraBoldItalic.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-ExtraBoldItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-ExtraLight.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-ExtraLight.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-ExtraLightItalic.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-ExtraLightItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-Italic.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-Italic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-Light.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-Light.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-LightItalic.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-LightItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-Medium.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-Medium.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-MediumItalic.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-MediumItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-Regular.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-Regular.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-SemiBold.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-SemiBold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-SemiBoldItalic.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-SemiBoldItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-Thin.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-Thin.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/lato/Lato-ThinItalic.ttf "https://github.com/google/fonts/blob/master/ofl/lato/Lato-ThinItalic.ttf?raw=true"

RUN mkdir -p /usr/share/fonts/truetype/inconsolata \
  && wget -O /usr/share/fonts/truetype/inconsolata/Inconsolata-Bold.ttf "https://github.com/google/fonts/blob/master/ofl/inconsolata/Inconsolata-Bold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/inconsolata/Inconsolata-Regular.ttf "https://github.com/google/fonts/blob/master/ofl/inconsolata/Inconsolata-Regular.ttf?raw=true"

RUN mkdir -p /usr/share/fonts/truetype/opensans \
  && wget -O /usr/share/fonts/truetype/opensans/OpenSans-Bold.ttf "https://github.com/google/fonts/blob/master/apache/opensans/OpenSans-Bold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/opensans/OpenSans-BoldItalic.ttf "https://github.com/google/fonts/blob/master/apache/opensans/OpenSans-BoldItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/opensans/OpenSans-ExtraBold.ttf "https://github.com/google/fonts/blob/master/apache/opensans/OpenSans-ExtraBold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/opensans/OpenSans-ExtraBoldItalic.ttf "https://github.com/google/fonts/blob/master/apache/opensans/OpenSans-ExtraBoldItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/opensans/OpenSans-Italic.ttf "https://github.com/google/fonts/blob/master/apache/opensans/OpenSans-Italic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/opensans/OpenSans-Light.ttf "https://github.com/google/fonts/blob/master/apache/opensans/OpenSans-Light.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/opensans/OpenSans-LightItalic.ttf "https://github.com/google/fonts/blob/master/apache/opensans/OpenSans-LightItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/opensans/OpenSans-Regular.ttf "https://github.com/google/fonts/blob/master/apache/opensans/OpenSans-Regular.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/opensans/OpenSans-SemiBold.ttf "https://github.com/google/fonts/blob/master/apache/opensans/OpenSans-SemiBold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/opensans/OpenSans-SemiBoldItalic.ttf "https://github.com/google/fonts/raw/4e24bf1805f1526cd1ce3e39447d5f8e6f1f6b67/apache/opensans/OpenSans-SemiboldItalic.ttf"

RUN mkdir -p /usr/share/fonts/truetype/firasans \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-Black.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-Black.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-BlackItalic.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-BlackItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-Bold.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-Bold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-BoldItalic.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-BoldItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-ExtraBold.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-ExtraBold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-ExtraBoldItalic.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-ExtraBoldItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-ExtraLight.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-ExtraLight.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-ExtraLightItalic.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-ExtraLightItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-Italic.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-Italic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-Light.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-Light.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-LightItalic.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-LightItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-Medium.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-Medium.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-MediumItalic.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-MediumItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-Regular.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-Regular.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-SemiBold.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-SemiBold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-SemiBoldItalic.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-SemiBoldItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-Thin.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-Thin.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firasans/FiraSans-ThinItalic.ttf "https://github.com/google/fonts/blob/master/ofl/firasans/FiraSans-ThinItalic.ttf?raw=true"

RUN mkdir -p /usr/share/fonts/truetype/firacode \
  && wget -O /usr/share/fonts/truetype/firacode/FiraCode-Bold.ttf "https://github.com/tonsky/FiraCode/blob/master/distr/ttf/FiraCode-Bold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firacode/FiraCode-Light.ttf "https://github.com/tonsky/FiraCode/blob/master/distr/ttf/FiraCode-Light.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firacode/FiraCode-Medium.ttf "https://github.com/tonsky/FiraCode/blob/master/distr/ttf/FiraCode-Medium.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firacode/FiraCode-Regular.ttf "https://github.com/tonsky/FiraCode/blob/master/distr/ttf/FiraCode-Regular.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/firacode/FiraCode-Retina.ttf "https://github.com/tonsky/FiraCode/blob/master/distr/ttf/FiraCode-Retina.ttf?raw=true" \
  && mkdir -p /usr/share/fonts/misc \
  && mkdir -p /usr/share/fonts/misc/firacode \
  && wget -O /usr/share/fonts/misc/firacode/FiraCode-Bold.woff "https://github.com/tonsky/FiraCode/blob/master/distr/woff/FiraCode-Bold.woff?raw=true" \
  && wget -O /usr/share/fonts/misc/firacode/FiraCode-Light.woff "https://github.com/tonsky/FiraCode/blob/master/distr/woff/FiraCode-Light.woff?raw=true" \
  && wget -O /usr/share/fonts/misc/firacode/FiraCode-Medium.woff "https://github.com/tonsky/FiraCode/blob/master/distr/woff/FiraCode-Medium.woff?raw=true" \
  && wget -O /usr/share/fonts/misc/firacode/FiraCode-Regular.woff "https://github.com/tonsky/FiraCode/blob/master/distr/woff/FiraCode-Regular.woff?raw=true" \
  && wget -O /usr/share/fonts/misc/firacode/FiraCode-Bold.woff2 "https://github.com/tonsky/FiraCode/blob/master/distr/woff2/FiraCode-Bold.woff2?raw=true" \
  && wget -O /usr/share/fonts/misc/firacode/FiraCode-Light.woff2 "https://github.com/tonsky/FiraCode/blob/master/distr/woff2/FiraCode-Light.woff2?raw=true" \
  && wget -O /usr/share/fonts/misc/firacode/FiraCode-Medium.woff2 "https://github.com/tonsky/FiraCode/blob/master/distr/woff2/FiraCode-Medium.woff2?raw=true" \
  && wget -O /usr/share/fonts/misc/firacode/FiraCode-Regular.woff2 "https://github.com/tonsky/FiraCode/blob/master/distr/woff2/FiraCode-Regular.woff2?raw=true"

RUN mkdir -p /usr/share/fonts/truetype/robotocondensed \
  && wget -O /usr/share/fonts/truetype/robotocondensed/RobotoCondensed-Bold.ttf "https://github.com/google/fonts/blob/master/apache/robotocondensed/RobotoCondensed-Bold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/robotocondensed/RobotoCondensed-BoldItalic.ttf "https://github.com/google/fonts/blob/master/apache/robotocondensed/RobotoCondensed-BoldItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/robotocondensed/RobotoCondensed-Italic.ttf "https://github.com/google/fonts/blob/master/apache/robotocondensed/RobotoCondensed-Italic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/robotocondensed/RobotoCondensed-Light.ttf "https://github.com/google/fonts/blob/master/apache/robotocondensed/RobotoCondensed-Light.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/robotocondensed/RobotoCondensed-LightItalic.ttf "https://github.com/google/fonts/blob/master/apache/robotocondensed/RobotoCondensed-LightItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/robotocondensed/RobotoCondensed-Regular.ttf "https://github.com/google/fonts/blob/master/apache/robotocondensed/RobotoCondensed-Regular.ttf?raw=true"

RUN mkdir -p /usr/share/fonts/truetype/ubuntumono \
  && wget -O /usr/share/fonts/truetype/ubuntumono/UbuntuMono-Bold.ttf "https://github.com/google/fonts/blob/master/ufl/ubuntumono/UbuntuMono-Bold.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/ubuntumono/UbuntuMono-BoldItalic.ttf "https://github.com/google/fonts/blob/master/ufl/ubuntumono/UbuntuMono-BoldItalic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/ubuntumono/UbuntuMono-Italic.ttf "https://github.com/google/fonts/blob/master/ufl/ubuntumono/UbuntuMono-Italic.ttf?raw=true" \
  && wget -O /usr/share/fonts/truetype/ubuntumono/UbuntuMono-Regular.ttf "https://github.com/google/fonts/blob/master/ufl/ubuntumono/UbuntuMono-Regular.ttf?raw=true"
  
RUN mkdir -p /usr/share/fonts/truetype/droidsans \
  && wget http://mirrors.ctan.org/fonts/droid.zip \
  && unzip droid.zip -d . \
  && cp droid/fonts/truetype/public/droid/DroidSans*.ttf /usr/share/fonts/truetype/droidsans \
  && rm -rf droid \
  && rm droid.zip

RUN mkdir -p /usr/share/fonts/truetype/droidserif \
  && wget -O /usr/share/fonts/truetype/droidserif/DroidSerif-Regular.ttf "https://fonts.gstatic.com/s/droidserif/v8/tDbI2oqRg1oM3QBjjcaDkOr9rAA.ttf" \
  && wget -O /usr/share/fonts/truetype/droidserif/DroidSerif-Bold.ttf "https://fonts.gstatic.com/s/droidserif/v8/tDbV2oqRg1oM3QBjjcaDkOJGiRD7OwQ.ttf" \
  && wget -O /usr/share/fonts/truetype/droidserif/DroidSerif-Italic.ttf "https://fonts.gstatic.com/s/droidserif/v8/tDbK2oqRg1oM3QBjjcaDkOr4nAfcGw.ttf" \
  && wget -O /usr/share/fonts/truetype/droidserif/DroidSerif-BoldItalic.ttf "https://fonts.gstatic.com/s/droidserif/v8/tDbX2oqRg1oM3QBjjcaDkOr4lLz5CwOnTQ.ttf"

RUN mkdir -p /usr/share/fonts/truetype/lucidaconsole \
  && wget -O /usr/share/fonts/truetype/lucidaconsole/LucidaConsole-Regular.ttf "https://github.com/elliotwoods/kimchiandchips/raw/master/oF/apps%20VS/PC%20Encode%203.0/bin/data/Lucida%20Console.ttf"

# Add Source Code Pro font type 1
RUN wget http://mirrors.ctan.org/install/fonts/sourcecodepro.tds.zip \
  && mkdir sourcecodepro \
  && unzip sourcecodepro.tds.zip -d sourcecodepro \
  && cp -R sourcecodepro/fonts/* /usr/share/fonts \
  && rm -rf sourcecodepro \
  && rm sourcecodepro.tds.zip

RUN fc-cache -fv

RUN wget -O google-chrome.deb "https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb" \
  && dpkg -i google-chrome.deb \
  && rm google-chrome.deb
