{%hackmd BJrTq20hE %}
# Linux離線安裝tcpdump
#### **環境:**
* CPU: ARMv7
* Debian

## 方法1: 更改source code 
> 錯誤方法，正確請看方法2
1. 使用MobaXterm的 Session ⇒ SFTP：可以把本地端資料丟到SSH連接端![](https://i.imgur.com/oysV305.png)
2. 將兩個壓縮檔丟過去
3. 跟著步驟：[參考網址](https://iter01.com/547952.html)
![](https://i.imgur.com/2JmeeUr.png)

4. 發現問題：no acceptable C compiler found in $PATH ⇒ GCC沒有裝
 ![](https://i.imgur.com/mCPISlz.png)
5. GCC安裝好後，執行 `./configure`，又發現問題：
![](https://i.imgur.com/Khp1iSl.png)
6. 最後換方法2⇒下載.deb檔

:::info
:bulb: **結論**：盡量不要使用上方source code方法，因為會發現有很多要下載或要處理的問題 (壓縮檔不是套件是source code)
:::

## 方法2: 下載.deb檔
1. Debian的tcpdump套件： [參考網址](https://packages.debian.org/stretch/tcpdump) 
2. 先確認上方三個相依套件有沒有： `apt list --installed | grep xxx` ⇒ 都有
3. 選擇i386架構：[參考網址](https://packages.debian.org/stretch/i386/tcpdump/download)
4. 點選頁面中的網址 [參考網址](http://security.debian.org/debian-security/pool/updates/main/t/tcpdump/tcpdump_4.9.3-1~deb9u2_i386.deb) 
⇒ 發現什麼東西都沒下載 ⇒ 好像自動已下載到某個地方
5. 利用這個網頁下載tcpdump：[參考網址](https://www.jinnsblog.com/2020/11/linux-ubuntu-offline-install-package.html)

```bash
$ apt-get install --download-only tcpdump
```
![](https://i.imgur.com/bsq82zC.png)

`$ ls` 確認有deb檔

![](https://i.imgur.com/tPqLgFC.png)

離線安裝套件
```bash
$ dpkg -i *.deb
```
![](https://i.imgur.com/hDImyiN.png)

6. 確認已下載好套件
```bash
$ apt list --installed | grep tcp
```
![](https://i.imgur.com/CGzv4su.png)

7. 利用這個網頁測試tcpdump可不可行：[參考網址](https://kknews.cc/zh-tw/code/vlp3yj4.html)

![](https://i.imgur.com/yKX5Hw3.png)

8. Uninstalled

![](https://i.imgur.com/ro80s4u.png)

