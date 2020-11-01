# Running TeamSpeak on Raspberry Pi

Steps:

1. Install Docker on RPi ([guide](https://phoenixnap.com/kb/docker-on-raspberry-pi))
2. Install QEMU on the RPi (`sudo apt install qemu-user-static`), this sets up everything necessary for interpreting x86_64 binaries with QEMU (binfmt_misc handlers in particular)
3. Clone or download this repository to `/home/pi/teamspeak-on-rpi` and `cd` to that directory
4. Prepare a Docker image for TeamSpeak: `docker build -t ts-rpi .`
5. Run TeamSpeak (see [here for details](https://hub.docker.com/_/teamspeak)): `docker run -p 9987:9987/udp -p 10011:10011 -p 30033:30033 -e TS3SERVER_LICENSE=accept ts-rpi`
