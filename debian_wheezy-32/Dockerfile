from debian:wheezy

RUN mv /etc/apt/sources.list /etc/apt/sources.list-orig; \
    awk '{print($0 " non-free");}' /etc/apt/sources.list-orig > /etc/apt/sources.list; \
    dpkg --add-architecture i386; \
    apt-get update; \
    apt-get -y upgrade; \
    apt-get install -y --force-yes rsync reprepro wget automake make tar python\
      libcurl4-gnutls-dev:i386 libreadline-dev:i386 \
      libdc1394-22-dev:i386 libraw1394-dev:i386 \
      libxml2-dev:i386 freetds-dev:i386 \
      libmotif-dev:i386 libxt-dev:i386 x11proto-print-dev:i386 \
      g++:i386 gfortran:i386 openjdk-7-jdk:i386; \
    mv /usr/bin/uil /usr/bin/uil32; \
    apt-get download \
      globus-common-progs:i386 globus-core:i386 libglobus-callout-dev:i386 \
      libglobus-callout0:i386 \
      libglobus-common-dev:i386 \
      libglobus-common0:i386 \
      libglobus-gridmap-callout-error-dev:i386 \
      libglobus-gridmap-callout-error0:i386 \
      libglobus-gsi-callback-dev:i386 \
      libglobus-gsi-callback0:i386 \
      libglobus-gsi-cert-utils-dev:i386 \
      libglobus-gsi-cert-utils0:i386 \
      libglobus-gsi-credential-dev:i386 \
      libglobus-gsi-credential1:i386 \
      libglobus-gsi-openssl-error-dev:i386 \
      libglobus-gsi-openssl-error0:i386 \
      libglobus-gsi-proxy-core-dev:i386 \
      libglobus-gsi-proxy-core0:i386 \
      libglobus-gsi-proxy-ssl-dev:i386 \
      libglobus-gsi-proxy-ssl1:i386 \
      libglobus-gsi-sysconfig-dev:i386 \
      libglobus-gsi-sysconfig1:i386 \
      libglobus-gss-assist-dev:i386 \
      libglobus-gss-assist3:i386 \
      libglobus-gssapi-error-dev:i386 \
      libglobus-gssapi-error2:i386 \
      libglobus-gssapi-gsi-dev:i386 \
      libglobus-gssapi-gsi4:i386 \
      libglobus-openssl-module-dev:i386 \
      libglobus-openssl-module0:i386 \
      libglobus-xio-dev:i386 \
      libglobus-xio-gsi-driver-dev:i386 \
      libglobus-xio-gsi-driver0:i386 \
      libglobus-xio0:i386; \
    for deb in *.deb; do dpkg-deb -xv ${deb} /; done; \
    ln -sf /usr/lib/i386-linux-gnu/pkgconfig/*.pc /usr/lib/pkgconfig/

COPY openssl.pc /usr/lib/pkgconfig/

