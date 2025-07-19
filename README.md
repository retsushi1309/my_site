
# serverの構築苦戦
conoha VPS
1.鍵の確認ls ~/.ssh/
2.ssh root@ipアドレス
3.キーの削除ssh-keygen -R　IPアドレス
ssh root@
4.インストール
sudo apt update
sudo apt install apache2 -y
sudo apt install nginx -y

#　ディレクトリの作成
sudo mkdir -p /var/www/html/praxisweb.work/public_html
パッションの設定
sudo chown -R www-data:www-data /var/www/html/praxisweb.work
sudo chmod -R 755 /var/www/html/praxisweb.work

# バーチャルホストの作成
sudo nano /etc/apache2/sites-available/praxisweb.work.conf
コピー
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    ServerName praxisweb.work
    ServerAlias www.praxisweb.work
    DocumentRoot /var/www/html/praxisweb.work/public_html

    <Directory /var/www/html/praxisweb.work/public_html>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
有効
sudo a2ensite praxisweb.work.conf
デフォルト無効（重要）
sudo a2dissite 000-default.conf
エラーの確認
sudo apache2ctl configtest
再起動
sudo systemctl reload apache2
