```
cat < /dev/tcp/$(stable_ip)/$(stable_port) | { IFS=: read -r ip port; ssh -t -p "$port" "root@$ip" < /dev/tty; }
```
