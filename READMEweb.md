# ファイルpcアップロード
scp -r . root@160.251.181.156:/var/www/html/praxisweb.work/public_html/
root@160.251.181.156's password: 
index.html                                    100%   23KB 152.8KB/s   00:00    

# SSH 
cdに移動
cd /var/www/html/praxisweb.work/public_html
確認
ls -la

# ポートの確認
sudo ufw status verbose
なければ追加
sudo ufw allow 80/tcp
sudo ufw reload
再起動
sudo systemctl restart apache2

# マックのキャッシュ削除
sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder
