

##### Read the hosts file
```
sudo cat /etc/hosts
```
```c
/*
# Do not remove the following line, or various programs
# that require network functionality will fail.
127.0.0.1               localhost.localdomain localhost
::1             localhost6.localdomain6 localhost6
*/
```

##### Check the hostname 
```
hostname
```
##### Check the fully qualified domain name
```
hostname -f
```

##### Read the sysconfig network file
```
sudo cat /etc/sysconfig/network
```

##### Check the DNS domain name
```
dnsdomainname
```

##### Get the IP address of the internal name server
```
cat /etc/resolv.conf
```

##### Check the routing table
```
route
```

##### Check the internal IP address
```
/sbin/ifconfig
```

##### Check the external IP address
```
wget http://ipinfo.io/ip -qO -
```

##### Run a speed test (just for fun)
```
mkdir ~/speedtest
cd ~/speedtest
wget https://raw.github.com/sivel/speedtest-cli/master/speedtest_cli.py
chmod +x speedtest_cli.py
./speedtest_cli.py
```


##### Edit the sysconfig network file
```
sudo nano /etc/sysconfig/network
```
```
HOSTNAME=[somehost]
```

##### Edit the hosts file
```
sudo nano /etc/hosts
```
```c
127.0.0.1  [somehost] [somehost].localdomain localhost localhost.localdomain
```

##### Reboot the system to pick up the new hostname and time zone information in all services and applications
```
sudo reboot
```

##### Check the hostname 
```
hostname
```
##### Check the fully qualified domain name
```
hostname -f
```

##### Check the DNS domain name
```
dnsdomainname
```
