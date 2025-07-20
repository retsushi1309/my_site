# ドメインようのディレクトリを作成
sudo mkdir -p /var/www/html/praxisweb.jp/public_html
# 2ディレクトリの所有者とパーミッションの設定
sudo chown -R www-data:www-data /var/www/html/praxisweb.jp
sudo chmod -R 755 /var/www/html/praxisweb.jp
# 3バーチャルホストの設定
sudo nano /etc/apache2/sites-available/praxisweb.jp.conf
コピー
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    ServerName praxisweb.jp
    ServerAlias www.praxisweb.jp
    DocumentRoot /var/www/html/praxisweb.jp/public_html

    <Directory /var/www/html/praxisweb.jp/public_html>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

# 有効化
sudo a2ensite praxisweb.jp.conf
エラーの確認
sudo apache2ctl configtest
再起動
sudo systemctl reload apache2

# PCからの転送
