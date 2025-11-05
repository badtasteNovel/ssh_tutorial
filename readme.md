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