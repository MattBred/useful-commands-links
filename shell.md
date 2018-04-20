* Find reverse DNS of a host
```sh
for HOST in $(host -t A example.com | awk '{print $4;}'); do host "${HOST}"; done
```

* Using rsync to recursively retrieve files
```sh
rsync -r -v --dry-run user@address:/remote/path/to/files /local/path/to/files
```

* Find out what ciphers are supported:
```sh
nmap --script ssl-enum-ciphers -p 443 www.example.com
```

* Get general SSL info:
```sh
openssl s_client -showcerts -connect www.example.com
```

* Find every file written to in the last 5 minutes
```sh
find / -mmin -5
```

* Clean up gitlab cache
```sh
/usr/share/gitlab-runner/clear-docker-cache
```

* Clean up old gitlab containers
```sh
sudo docker rm -v $(sudo docker ps --filter "status=exited" | grep -E "Exited \([0-9]\) [1-9] months ago" | awk '{print $1}')
```
