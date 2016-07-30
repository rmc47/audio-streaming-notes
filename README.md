# Notes on audio streaming...

## Raspberry Pi Cirrus Logic audio card

- Use Raspbian Jessie
- Download the pre-compiled kernel from http://www.horus.com/~hias/cirrus-driver.html
- Remember to enable the new card with `dtoverlay=rpi-cirrus-wm5102` in `config.txt` and enable the modules as described above
- Verify with `aplay --list-devices`, which should show a `sndrpiwsp`

## Icecast

- Install with `apt-get install icecast2`

## Liquidsoap

- Install both `liquidsoap` and `liquidsoap-plugin-all` to get the alsa plugins
- Simple stream: `liquidsoap 'output.icecast(%vorbis.cbr(bitrate=320),host="foo",port=8000,password="bar",mount="liq.ogg",input.alsa(device="hw:sndrpiwsp"),fallible=true)'`

## Recording Icecast stream

- fIcy: https://www.thregr.org/~wavexx/software/fIcy/
