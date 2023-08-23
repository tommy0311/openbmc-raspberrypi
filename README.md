# openbmc-raspberrypi

## How to build openbmc for raspberry pi

1. git clone [https://gitlab.com/vertiv-co/its/developers/tommychen2/openbmc-raspberrypi.git](https://github.com/tommy0311/openbmc-raspberrypi.git)
2. cd openbmc-raspberrypi
3. kas checkout kas-poky-rpi.yml
4. echo 'LICENSE_FLAGS_ACCEPTED = "synaptics-killswitch" ' >> layers/openbmc/meta-raspberrypi/conf/layer.conf
5. kas build kas-poky-rpi.yml
6. install [balenaetcher](https://etcher.balena.io/) in Windows
7. insert SD_CARD in Windows
8. copy /build/tmp/deploy/images/raspberrypi3-64/obmc-phosphor-image-raspberrypi3-64.rpi-sdimg to Windows
9. Use balenaetcher to flash .rpi-sdimg to SD_CARD
10. Insert SD_CARD to raspberrypi and power up

## webgui & ssh default username/password
- root/0penBmc

## known issues
- bmcweb start fail <br/>
$ touch /var/log/redfish <br/>
$ systemctl restart bmcweb

- docker run fail <br/>
// Need to update system datetime timestamp to now <br/>
$ date +%s -s @1692692547 

## Reference
- https://meta-raspberrypi.readthedocs.io/en/latest/
- https://kas.readthedocs.io/en/latest/
- https://m5p3nc3r.github.io/Adding_docker_to_yocto/
