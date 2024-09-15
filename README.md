# Home Assistant Raspberry Pi I2C custom integration

Since the removal of GPIO support from home assistant pyscript isn't able to use I2C modules via Adafruit-Blinka.

This project is supposed to re-enable that support.

Python modules: ['sysv-ipc', 'adafruit-circuitpython-ads1x15', 'Adafruit-Blinka']

Steps to manually reenable functionality right now:
- ssh to HAOS-Machine
- docker exec -it homeassistant /bin/bash -c "apk add gcc libc-dev && mkdir /root/tmp && mount /root/tmp /tmp && python -m pip install adafruit-circuitpython-ads1x15 && umount /tmp && rm -rf /root/tmp && apk del gcc libc-dev"

This has to be brought into a HACS conform module to prevent manual intervention.
