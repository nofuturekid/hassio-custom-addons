ARG BUILD_FROM
FROM $BUILD_FROM

RUN apk add --no-cache \
  bash \
  gcc \
  libusb \
  musl-dev \
  openssl-dev \
  python \
  python-dev \
  py2-pip \
  py-yaml \
  jq

RUN pip --no-cache-dir install --upgrade pip && \
  pip --no-cache-dir install flask && \
  pip --no-cache-dir install adb==1.2.0 && \
  pip --no-cache-dir install --upgrade https://github.com/gollo/python-firetv/zipball/master

COPY run.sh /
COPY json2yaml.py /
RUN chmod a+x /run.sh json2yaml.py

CMD [ "/run.sh" ]
