---
description: Wave を導入するにあたっての準備です。
---

# 事前準備

**既にWaveのアカウントを取得している場合にはこのフローは必要ありません。**

* Alphaus のHourlyレポート解析を有効にするために、お客様のAWSアカウントで実施する必要がある作業と、Alphaus に提出する情報について記述します。
* 作業後、Alphaus に提出する情報については以下の通りです。 各段階の作業で控えていただくようお願いいたします。\(作業後でも確認可能です。\)

```text
- AWSアカウントのID (数字12桁)

- 作成したレポートの情報

    - レポート名

    - S3バケット

    - レポートパスのプレフィックス、またはレポートのパス

- 特定バケット許可用の IAMロールのARN (例: arn:aws:iam::xxxxxxxxxxxx:role/crossacounnt-access-for-mobingi)
```

## 手順 1 : S3バケットおよびHourlyレポートの作成\(任意\)  <a id="step1"></a>

* 請求情報を共有するAWSのアカウントで、Hourlyレポートを作成します。
* 以下の条件に当てはまるレポート定義がすでにある場合、この作業をスキップしてすることが可能です。

  `時間単位: 時間別`

  `レポートに含める項目で リソースID が有効`

  `バケット内にAlphausが 閲覧してはいけないオブジェクト を含まない(バケット全体に読み取りアクセスを付与するため)`

### 手順1-1: **S3バケットの作成**

* S3コンソールから任意の名称でバケットを作成します。オプションはデフォルトで構いません。

  レポートの出力先として利用するため、バケット名を控えておいてください。

### 手順1-2: **Hourlyレポートの作成**

* AWSのマネジメントコンソールから、『請求』を開き『Cost & Usage Reports 』メニューへ移動します。

レポートの作成へ進みます。

![](../.gitbook/assets/billing_management_console.png)

* 『ステップ 1: レポートの明細項目』を以下の要領で記入して次に進めます。
  * レポート名：任意
  * **リソースIDのインクルード**：チェック
  * データの更新設定：チェック推奨

![](../.gitbook/assets/ming-cheng-wei-she-ding-7.png)

* 『ステップ 2: 配信オプション』では、S3バケットの操作を含めるため、以下手順で進めます。
  * S3バケット名の設定ボタンをクリック
  * 『ステップ 1/2: S3 バケットの設定』で既存のバケットを選択
  * 『ステップ 2/2: ポリシーの確認』のポリシーの確認にチェックを入れ保存

![](../.gitbook/assets/billing_management_console-3.png)

![](../.gitbook/assets/billing_management_console-4.png)

![](../.gitbook/assets/billing_management_console-5.png)

* 検証で「有効なバケット」と出ていることを確認し、下記の設定を行います。
  * レポートパスのプレフィックス: 任意 \(※なしでも構いません\)
  * 使用料の時間詳細度：**時間別**
  * レポートのバージョニング：新しいメールバージョンの作成
  * **レポートデータ統合の有効化: チェックしない**
  * 圧縮タイプ: GZIP もしくは ZIP を選択

{% hint style="danger" %}
レポートデータ統合を有効化すると正常に動かない場合があります。
{% endhint %}

* 『ステップ 3: 確認』表示されている内容に間違いがない確認し、完了します。

![](../.gitbook/assets/sukurnshotto-2019-06-14-144714.png)

## 手順 2 :読み取り権限を委譲するIAMロールの作成  <a id="step2"></a>

AWSのマネジメントコンソールから、IAMサービスを開き、『ロール』&gt;&gt; 『ロールの作成』メニューへ移動します。

![](../.gitbook/assets/iam_management_console-2.png)

『信頼されたエンティティの種類を選択』で、「別のAWSアカウントを」選択し、以下のAlphaus のアカウントIDを入力します。

* **Alphaus アカウントID: 131920598436**

![](../.gitbook/assets/iam_management_console-3.png)

「Attach アクセス権限ポリシー」メニューで、『ポリシーの作成』を選択します。

![](../.gitbook/assets/iam_management_console-4.png)

別のタブ\(ウィンドウ\)で「ポリシーの作成」メニューが開くので、入力形式にJSONを選択し、以下の内容でポリシーを入力します。 Resourceの`{replace_to_report_bucket}`部分を **レポートに使用するバケット名** に置き換えてください。

```bash
{
    "Version": "2012-10-17",
   "Statement": [
         {
               "Effect": "Allow",
               "Action": [
                     "s3:Get*",
                     "s3:List*"
               ],
               "Resource": [
                     "arn:aws:s3:::{replace_to_report_bucket}",
                     "arn:aws:s3:::{replace_to_report_bucket}/*"
               ]
         }
   ]
}
```

![](../.gitbook/assets/iam_management_console-5.png)

![](../.gitbook/assets/iam_management_console-6.png)

「ポリシーの確認」へ進み、以下の項目を入力してポリシーを作成します。

* 名前: 任意\(※必須\)
* 説明: 任意

![](../.gitbook/assets/iam_management_console-7.png)

『ロールの作成』メニューに戻り、リストを更新し、先ほど作成したポリシーを表示します。 チェックを有効にして、確認へ進みます。

![](../.gitbook/assets/iam_management_console.png)

『次のステップ: タグ』をクリック。

* タグは任意で設定してください。

「確認」メニューで、以下の項目を入力します。

* ロール名: 任意\(※必須\)
* ロールの説明: 任意

「信頼されたエンティティ」、「ポリシー」が適用されていることを確認し、ロールを作成します。

![](../.gitbook/assets/iam_management_console-9.png)

作成したロールのARNを控えます。

![](../.gitbook/assets/iam_management_console-10.png)
