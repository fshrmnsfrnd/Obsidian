---
Thema:
  - "[[HomeLab]]"
---
>nginx ("_engine x_") is an HTTP web server, reverse proxy, content cache, load balancer, TCP/UDP proxy server, and mail proxy server.

https://nginx.org/en/docs/index.html

# SSL Zertifikat erstellen
Um ein SSL Zertifikat über Let's Encrypt zu bekommen müssen Port 80 und Port 443 aus dem Internet erreichbar sein
Außerdem muss es eine gültige öffentliche Domain sein

# Host hinzufügen
Hosts -> Add Proxy Host 

**Details:**

| Field                 | Value                         |
| --------------------- | ----------------------------- |
| Domain Names          | Public Domain Name            |
| Scheme                | Required Scheme of the Server |
| Forward Hostname / IP | Best Practise: Hostname       |
| Forward Port          | Port of the Server            |
