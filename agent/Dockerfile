FROM jetbrains/teamcity-minimal-agent
# Install Packages
ENV DEBCONF_NOWARNINGS yes
RUN dpkg --add-architecture i386 && \
  apt-get update && \
  apt-get install -y --no-install-recommends curl zip unzip git wget gnupg apt-transport-https chromium-browser chromium-chromedriver && \
  curl -sL https://deb.nodesource.com/setup_10.x | bash - && \
  apt-get --quiet install --yes nodejs && \
  apt-get clean && \
  apt-get autoremove && \
  rm -rf /var/lib/apt/list

ENV CHROME_BIN /usr/bin/chromium-browser
ENV CHROMIUM_FLAGS "--disable-gpu --no-sandbox --headless"
RUN ln -s /usr/lib/chromium-browser/chromedriver /usr/bin/ && \
  rm /etc/chromium-browser/default