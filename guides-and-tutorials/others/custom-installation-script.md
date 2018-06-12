# カスタムスクリプトを記述する

Dockerコンテナ作成時に追加でミドルウェアのインストールや設定変更を実行するために、bash形式のスクリプトコードを挿入することができます。Dockerイメージに含まれていないものをインストールしたいときなどにご利用ください。

![](../../.gitbook/assets/custom-script.png)

カスタムスクリプトが実行されるためには`mobingi-init.sh`ファイルをリポジトリの**ルート**に配置しておくだけで、自動的に実行を開始します。

スクリプト例:  
下記のスクリプトはComposerが必要なPHPで書かれたプロジェクトであり、自動的に追加インストールを実行します。

```bash
sudo apt-get update
sudo apt-get -y install curl
sudo su
curl -sS https://getcomposer.org/installer | php
php composer.phar install
```

さらに、実行結果のログはアプリケーション環境の詳細ページから見ることが可能です。Logsタブをクリック、インスタンスIDを選び、ドロップダウンメニューにあるmoDaemonかStartupをクリックするだけでログが閲覧できます。

![](../../.gitbook/assets/custom-script2jp.png)

