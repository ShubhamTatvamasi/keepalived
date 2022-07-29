# keepalived

Install keepalived:
```bash
sudo apt install keepalived -y
```

Update config:
```bash
sudo vim /etc/keepalived/keepalived.conf
```
```
# VM-1
vrrp_instance VI_1 {
        state MASTER
        interface enp0s1
        virtual_router_id 51
        priority 255
        advert_int 1
        authentication {
              auth_type PASS
              auth_pass 12345
        }
        virtual_ipaddress {
              192.168.64.100/24
        }
}
```
```
# VM-2
vrrp_instance VI_1 {
        state BACKUP
        interface enp0s1
        virtual_router_id 51
        priority 254
        advert_int 1
        authentication {
              auth_type PASS
              auth_pass 12345
        }
        virtual_ipaddress {
              192.168.64.100/24
        }
}
```

Restart keepalived service:
```bash
sudo systemctl restart keepalived
sudo systemctl status keepalived
```

