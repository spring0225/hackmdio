{%hackmd BJrTq20hE %}
# 架設 Web Server : nginx
```bash
$ sudo apt install nginx
```
![](https://i.imgur.com/IJHrMZ8.png)

Nginx預設會啟用HTTP，TCP連接埠為HTTP預設的80，查看Nginx是否有確實安裝成功：
![](https://i.imgur.com/f3SKaTc.png)

1. `sudo -i` 回到root (問題:原本用su，他說沒有權限)
2. `cd /var/www/html`
![](https://i.imgur.com/QsroVpt.png)
3. `vim index.html` 新增檔案
![](https://i.imgur.com/CJkxiqe.png)
4. 按i/a鍵可以編輯，按Esc回到命令模式，:wq! 儲存檔案並離開，:q 離開
5. 打開網頁就可以看到:
 ![](https://i.imgur.com/vCSC7pD.png)
