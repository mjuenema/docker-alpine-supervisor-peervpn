# Docker image running PeerVPN under Supervisor.

This is a variation on `mjuenema/alpine-peervpn` were PeerVPN
is started by Supervisor. 

## Usage

Pull the image from Dockerhub.

    docker pull mjuenema/alpine-supervisor-peervpn

This Docker image is meant to serve as a base image for own customisations.
The included `/etc/peervpn.conf` contains default values and MUST be
overwritten to be useful. 

```
FROM mjuenema/alpine-supervisor-peervpn

COPY peervpn.conf /etc/peervpn.conf
```

Build and run your image like shown below, where the UDP port matches
the setting in `peervpn.conf`.

```
docker run --name=NAME -p 7000:7000/udp --privileged -d <image>
```

## Author

Markus Juenemann <markus@juenemann.net>

## Changelog

### `0.1`

Initial version.
