# git online
**與git建立ssh連結**
# workflow
**git主機與其他主機進行ssh連線**
# cpanel
**cpanel主機ssh金鑰配置，若不是cpanel gui 請略過**

# ssh權限問題
請開啟ssh-agent 處理問題，請設置ssh-agent 服務進程，每次電腦打開都開啟
```cmd
sc config ssh-agent start=auto
```
手動開啟
```cmd
net start ssh-agent
```
```cmd
ssh-add <private-key-path>
```
# 檢查金鑰是否匹配
```cmd
ssh-keygen -y -f <檔案路徑>
```


# 最重要
因為自動化維運不會填寫passphrase因此，使用時必須要限定特定ip
<img width="933" height="490" alt="image" src="https://github.com/user-attachments/assets/4b6464db-a3d3-4f3a-a9f6-cf2566990d27" />
<img width="903" height="419" alt="image" src="https://github.com/user-attachments/assets/1f95e0cf-36c5-4c0b-9cce-e29b010e5472" />
```bash
from=<computer-ip>,no-port-forwarding,no-X11-forwarding,no-agent-forwarding,no-pty <金鑰>
```
# 多台客戶端維運主機
<img width="858" height="245" alt="image" src="https://github.com/user-attachments/assets/235a0810-d873-4f33-9e1d-30ab868695dd" />

# 開放3306阜，進行mysql維運遠端gui維運，那就不要寫``no-port-forwarding``，改寫``permitopen="127.0.0.1:3306"``
```
from="192.168.0.65",permitopen="127.0.0.1:3306",no-X11-forwarding,no-agent-forwarding,no-pty
```
# 可以將對方伺服器的port 開放出來(請維持終端開啟)
ssh -L 5433:127.0.0.1:5432 <ssh-host>(可以是來自config的 HOST 名稱 就不用手動填寫金鑰)

# ~/.ssh/authorized_keys 的作用:
- 規範客戶端可以登入的key
# known host 查找
1. ```ssh-keygen -lf <path-to-host-key>.pub```
2. 這是host-key的public-key 並不是自己所建立的public-key，而是該主機自帶的。 請查找自己加密方式對應的 ssh-host-key 通常會放在/etc/ssh 裡面。
