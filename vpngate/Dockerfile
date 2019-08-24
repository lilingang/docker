FROM alpine

RUN apk add --no-cache openvpn python3 git && \
pip3 install beautifulsoup4 && \
pip3 install html5lib && \
cd / && \
git clone https://github.com/lilingang/vpngate.git && \
cd /vpngate && \
python3 main.py



CMD ["tail","-f","/etc/hosts"]
