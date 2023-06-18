FROM balenalib/raspberry-pi-debian:latest as base
SHELL ["/bin/bash", "-o", "pipefail", "-c"]
RUN curl -sSfL https://repo.homebridge.io/KEY.gpg | gpg --dearmor | tee /usr/share/keyrings/homebridge.gpg  > /dev/null \
    && echo "deb [signed-by=/usr/share/keyrings/homebridge.gpg] https://repo.homebridge.io stable main" | tee /etc/apt/sources.list.d/homebridge.list > /dev/null \
    && apt-get update \
    && apt-get install homebridge -y \
    && apt-get upgrade -y

ENTRYPOINT ["/opt/homebridge/start.sh", "--allow-root"]

