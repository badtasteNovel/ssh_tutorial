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
