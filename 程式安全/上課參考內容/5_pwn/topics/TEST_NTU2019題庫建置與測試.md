## 建置題目

- 此次測試以[kali linux 2019(64bit)](https://drive.google.com/file/d/1awLNHsJKgga2W0XFycnBmPEgzx4221Wi/view?usp=sharing) 版本為準
  - 此版本已安裝docker
  - 可使用此docker version 檢查docker 版本
  - 需使用docker-compos來一次啟動多個docker
 
### [安裝docker-compose](https://computingforgeeks.com/how-to-install-latest-docker-compose-on-linux/)
```
curl -s https://api.github.com/repos/docker/compose/releases/latest | grep browser_download_url  | grep docker-compose-linux-x86_64 | cut -d '"' -f 4 | wget -qi -

chmod +x docker-compose-linux-x86_64

sudo mv docker-compose-linux-x86_64 /usr/local/bin/docker-compose

docker-compose version
```

### 下載安裝[張元NTU-PWN](https://github.com/yuawn/NTU-Computer-Security-2019)

- 下載 ==> git clone https://github.com/yuawn/NTU-Computer-Security-2019.git
- 切換到第一周的目錄 ==> cd week1 # week2 week3
- 啟動第一周的各題目 ==> docker-compose up -d
- 檢視啟動的dockers與連線的port ==> docker-compose ps
```
NAME                COMMAND                  SERVICE             STATUS              PORTS
week1-bof-1         "/usr/sbin/xinetd -d…"   bof                 running             0.0.0.0:10170->4597/tcp
week1-casino-1      "/usr/sbin/xinetd -d…"   casino              running             0.0.0.0:10172->4597/tcp
week1-orw-1         "/usr/sbin/xinetd -d…"   orw                 running             0.0.0.0:10171->4597/tcp
````

## 你的writeups
