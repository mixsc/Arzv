# Getting websocket dropbear
wget -q -O /usr/local/bin/ws-dropbear "https://raw.githubusercontent.com/mixsc/Arzv/main/tools/ws-dropbear"
chmod +x /usr/local/bin/ws-dropbear

# Installing Service
cat > /etc/systemd/system/ws-dropbear.service << END
[Unit]
Description=Ssh Websocket By Arz
Documentation=https://arzvpnstore.biz.id
After=network.target nss-lookup.target

[Service]
Type=simple
User=root
CapabilityBoundingSet=CAP_NET_ADMIN CAP_NET_BIND_SERVICE
AmbientCapabilities=CAP_NET_ADMIN CAP_NET_BIND_SERVICE
NoNewPrivileges=true
ExecStart=/usr/bin/python2 -O /usr/local/bin/ws-dropbear 2082
Restart=on-failure

[Install]
WantedBy=multi-user.target
END

systemctl daemon-reload >/dev/null 2>&1
systemctl enable ws-dropbear >/dev/null 2>&1
systemctl start ws-dropbear >/dev/null 2>&1
systemctl restart ws-dropbear >/dev/null 2>&1

clear 
