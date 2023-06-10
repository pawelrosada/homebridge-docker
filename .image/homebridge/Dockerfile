FROM balenalib/raspberry-pi-debian as base
RUN curl -sSfL https://repo.homebridge.io/KEY.gpg | sudo gpg --dearmor | sudo tee /usr/share/keyrings/homebridge.gpg  > /dev/null \
    && echo "deb [signed-by=/usr/share/keyrings/homebridge.gpg] https://repo.homebridge.io stable main" | sudo tee /etc/apt/sources.list.d/homebridge.list > /dev/null \
    && sudo apt-get update \
    && sudo apt-get install homebridge -y

ENTRYPOINT ["/opt/homebridge/start.sh", "--allow-root"]

