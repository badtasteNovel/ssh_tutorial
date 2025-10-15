### 以一台cpanel主機為例 其根目錄為 /home/```主機名稱```
```
target: "/home/warriord/test_ssh/websocketExample"
```
### 因此有個固定的前綴 之後才是檔案位置

### ssh 開放的port 取決於每台主機的不同。非固定

### host 為頂層網域，非子域名。
ex:XXX.xxx-xxx.com
其頂層網域為:xxx-xxx.com
### userName 為該主機的登入使用者名稱。

### ssh 為private key 另一端主機方請設定一份公鑰達成非對稱性加密。
```
ssh-keygen \
    -m PEM \ 方式 預設:PEM
    -t rsa \編碼模式
    -b 4096 \ 預設:4096
    -C "azureuser@myserver" \ 註解
    -f ~/.ssh/id_rsa \ ~/簡短版路徑若不行，請使用fullPath
    -N mypassphrase 通關密碼 github個人帳號不要設置
```