FROM rhasspy/rhasspy:2.5.9
LABEL maintainer="Michael Hansen <hansen.mike@gmail.com>"

ENV LANG C.UTF-8
ENV CONFIG_PATH /data/options.json

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
      git \
      alsa-utils \
      dkms \
      i2c-tools \
      libasound2-plugins \
    && git clone "https://github.com/respeaker/seeed-voicecard" \
    && cd seeed-voicecard \
    && chmod a+x ./install.sh \
    && rm -rf .git \
    && apt-get purge -y --auto-remove git



COPY run.sh /

ENTRYPOINT ["/run.sh"]
