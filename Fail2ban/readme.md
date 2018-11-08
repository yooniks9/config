## sample of /etc/fail2ban/jail.local ; we knew that are attacks to the server, so maxretry will be set = 1, and bantime = 2592000 (1 month)

```
[DEFAULT]

ignoreip = 127.0.0.1/8 172.16.0.1/12
bantime  = 6000
maxretry = 3

backend = polling

destemail = root@localhost
sendername = Fail2Ban
banaction = iptables-multiport
mta = sendmail
protocol = tcp
chain = INPUT

action_ = %(banaction)s[name=%(__name__)s, port="%(port)s", protocol="%(protocol)s", chain="%(chain)s"]

action_mw = %(banaction)s[name=%(__name__)s, port="%(port)s", protocol="%(protocol)s", chain="%(chain)s"]
              %(mta)s-whois[name=%(__name__)s, dest="%(destemail)s", protocol="%(protocol)s", chain="%(chain)s", sendername="%(sendern$

action_mwl = %(banaction)s[name=%(__name__)s, port="%(port)s", protocol="%(protocol)s", chain="%(chain)s"]
               %(mta)s-whois-lines[name=%(__name__)s, dest="%(destemail)s", logpath=%(logpath)s, chain="%(chain)s", sendername="%(send$

action = %(action_)s

[zombievault]
enabled = true
port = http,https
filter = hellfire
logpath = /var/log/apache2/*access.log
bantime = 2592000
findtime = 600
maxretry = 1
```