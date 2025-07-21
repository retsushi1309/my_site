# Apacheの動作確認
SHHからsudo systemctl status httpd
ActiveならOK
# Apacheのインストール
sudo apt update
sudo apt install apache2 -y
# Apacheの起動と自動起動設定
sudo systemctl start apache2
sudo systemctl enable apache2
# Apacheのステータス確認
sudo systemctl status apache2
# ファイヤウォールの確認
sudo ufw allow 'Apache'
sudo ufw enable
sudo ufw status
