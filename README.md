# サイトの形と構成が完成✅

# 画像の選定　✅

# JSで動きを作る
  内容の整理

# サイトの充実のため
Django でブログの作成
Django で問い合わせフォームのシステム

# serverの構築苦戦
conoha VPS
1.鍵の確認ls ~/.ssh/
2.ssh root@ipアドレス
3.キーの削除ssh-keygen -R　IPアドレス
ssh root@
4.インストール
sudo apt update
sudo apt install nginx -y
5.ルートの作成
sudo nano /etc/nginx/sites-available/default

6.テスト、再起動
sudo nginx -t
sudo systemctl restart nginx
7.ディレクトリの作成
sudo mkdir -p /var/www/web/
8.ローカルから転送反映させるため
scp -r /Users/pc/web/html/ root@160.251.181.156:/var/www/web/

9.ファイヤウォールの確認
sudo ufw status verbose
ポート８０の追加
sudo ufw allow 80/tcp
