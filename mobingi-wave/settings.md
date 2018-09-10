# 各種設定・変更

コンソール右上のドロップダウンメニューから設定を選択します。

![](../.gitbook/assets/snip20180910_5.png)

### 設定画面でできること

1. ログインID（メールアドレス）の変更 
2. パスワードの変更

   * 現在のパスワードを忘れてしまった場合はお手数ですが、[ログインページより再設定](https://docs.mobingi.com/v/wave/mobingi-wave/settings#resetpw)できます。

3. 言語の選択

   * 日本語、英語、中国語に対応しています。

4. チャート設定
   * ダッシュボードのチャートに表示するサービスを最大5つまで選択できます。（デフォルトはEC2のみ選択） 
5. 通知設定

   * レポート画面から設定した予算を越えると、メールもしくはslackに通知が飛びます。
   * Slackに通知する場合`webhookURL`を入力する必要があります。
     1. Slackにログインし通知先のSlackチャンネルを作成（既にある場合は必要なし）
     2. [https://slack.com/services/new/incoming-webhook](https://slack.com/services/new/incoming-webhook)にアクセス
     3. 通知先チャンネルを選択後`Add Incoming WebHooks integration`をクリック
     4. `Descriptive Label`等の設定等のを変更する場合は`Save Settings`する
     5. `Webhook URL` の `Copy URL` をクリック
     6. コピーしたWebhook URLをWaveに貼り付け

6. Additional Setting
   * 割引率と為替レートの設定ができます。利用方法については[割引と為替の適用](https://docs.mobingi.com/v/wave/mobingi-wave/apply-jpy)をご覧ください。

## 設定：レポートページ

### 予算設定

レポートページから設定・変更できる作業です。

![](../.gitbook/assets/snip20180806_14.png)

レポートページから対象のアカウントを選択し、アカウント名したの`予算設定`ボタンをクリック。ポップアップより日、月ごとの予算が設定できます。

予算をオーバーした場合にはメール・Slackにて通知されます。通知設定は本ページ内の`3.通知設定`をご覧ください。

### アカウント名の変更

アカウント名右の`Edit`をクリックするとWave上の名前の表記が変更できます。

![](../.gitbook/assets/image.png)

## パスワードの再設定 {#resetpw}

パスワードを忘れた際にログインページからのリンクで再設定できます。

![](../.gitbook/assets/snip20180910_1.png)

1. `パスワードの再設定`をクリック
2. メールアドレスを入力
3. メールに通知された6桁の番号を入力して認証
4. パスワードを再設定

