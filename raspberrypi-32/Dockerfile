from mdsplus/docker:ubuntu14-32

#RUN   wget -q -O - --no-check-certificate https://github.com/raspberrypi/tools/archive/master.tar.gz | tar zxCf / - tools-master/arm-bcm2708/gcc-linaro-arm-linux-gnueabihf-raspbian; \
#      ln -sf /tools-master/arm-bcm2708/gcc-linaro-arm-linux-gnueabihf-raspbian/arm-linux-gnueabihf/include /usr/include/arm-linux-gnueabihf

COPY  *.tar.gz /
RUN   mkdir -p /raspberrypi-rootfs; \
      cd /raspberrypi-rootfs; \
      tar zxf /rootfs.tar.gz; \
      cd /; \
      tar zxf gcc-arm-raspbian.tar.gz; \
      ln -sf /gcc-linaro-arm-linux-gnueabihf-raspbian/arm-linux-gnueabihf/include /usr/include/arm-linux-gnueabihf; \
      mkdir -p /raspberrypi-include; \
      cd /raspberrypi-include; \
      ln -sf /raspberrypi-rootfs/usr/include/Mrm ./; \
      ln -sf /raspberrypi-rootfs/usr/include/X11 ./; \
      ln -sf /raspberrypi-rootfs/usr/include/Xm ./; \
      ln -sf /raspberrypi-rootfs/usr/include/readline ./; \
      ln -sf /raspberrypi-rootfs/usr/include/curl ./; \
      ln -sf /usr/include/sybdb.h ./; \
      ln -sf /usr/include/syberror.h ./; \
      ln -sf /usr/include/sybfront.h ./; \
      ln -sf /usr/include/tds_sysdep_public.h ./; \
      ln -sf /usr/bin/uil32 /usr/bin/uil


