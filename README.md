# dyndns
dynamic DNS on Linux with systemd

Register at a dynDNS provider, you can find them easily online. They mostly use a trick that your server is a client, downloads a file from them, which tells them your IP. They then update that IP. 

```
curl -3sSL -o dyndns.service https://github.com/boredsquirrel/dyndns/raw/refs/heads/main/dyndns.service && sudo mv dyndns.service /etc/systemd/system/
curl -3sSL -o dyndns.timer https://github.com/boredsquirrel/dyndns/raw/refs/heads/main/dyndns.timer && sudo mv dyndns.timer /etc/systemd/system/
```

Make sure to change the service file to use your correct URL, then activate:

```
systemctl enable --now dyndns
```
