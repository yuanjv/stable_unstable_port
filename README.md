```
cat < /dev/tcp/$(stable_ip)/$(stable_port) | { IFS=: read -r ip port; ssh -t -p "$port" "$(target_user)@$ip" < /dev/tty; }
```

```
while true; do nc -l -p $(wanted_local_port) -c "nc $(nc $(stable_ip) $(stable_port) | sed 's/:/ /')" 1>/dev/null 2>/dev/null; done
```



