# 権限

最新の権限リストは[Githubのページ](%20https://github.com/mobingi/rbac-permissions)をご確認ください。 

以下テーブルのリストは全てAlphaus のサービス内で適用されるものです。

## USER 権限 <a id="user-permissions"></a>

以下はユーザーの管理において適用される権限一覧です。

| Permission | Description |
| :--- | :--- |
| `Admin` | 一切の制限がない権限です。ルートユーザーはデフォルトで Admin 権限となります。 |
| `ReadOnly` | ユーザー情報の閲覧権限です。 |
| `ModifyUsers` | ユーザー情報の変更権限です。 |

## ROLE 権限

以下はロールの管理において適用される権限一覧です。

| Permission | Description |
| :--- | :--- |
| `Admin` | 一切の制限がない権限です。ルートユーザーはデフォルトで Admin 権限となります。 |
| `ReadOnly` | View RBAC 権限、ロール、マッピングの閲覧が可能です。 |
| `ModifyRoles` | ロールの内容の変更が可能です。 |
| `ModifyUserRoles` | ユーザーに付与されているロールの変更が可能です。 |

## WAVE 権限 <a id="wave-permissions"></a>

以下はWave の管理において適用される権限一覧です。 

| Permission | Description |
| :--- | :--- |
| `Admin` | 一切の制限がない権限です。ルートユーザーはデフォルトで Admin 権限となります。 |
| `DownloadBulk` | CSVの一括ダウンロード権限です。 |
| `ModifyAccountSettings` | 「アカウント情報」の変更権限です。 |
| `ModifyGroups` | 「グループ」の編集が可能になります。 |
| `ModifySettings` | 「設定」の変更が可能です。 |
| `ModifyTags` | 「タグ」ページの機能です。 |
| `ReadAccount` | 「アカウント」の閲覧権限です。 |
| `ReadAccountSettings` | アカウントの設定閲覧権限です。 |
| `ReadGroups` | 「グループ」の閲覧権限です。 |
| `ReadInvoice` | 請求書ページの閲覧権限です。 |
| `ReadSettings` | 「設定」の閲覧権限です。 |
| `ReadTags` | 「タグ」ページの閲覧権限です。 |

## RIPPLE 権限 <a id="ripple-permissions"></a>

以下はRipple の管理において適用される権限一覧です。

| Permission | Description |
| :--- | :--- |
| `Admin` | 一切の制限がない権限です。ルートユーザーはデフォルトで Admin 権限となります。 |
| `ModifyAccount` | 「アカウント」ページのアカウントの追加、変更、削除が可能です。 |
| `ModifyBillingGroup` | 「請求グループ」ページの請求グループの追加、変更、削除が可能です。 |
| `ModifyInvoice` | 「請求書の作成ページ」にて請求書作成、請求書設定の変更をする権限です。 |
| `ModifyInvoiceSettings` | 「環境設定」メニュー &gt;「請求書設定」ページを変更する権限です。 |
| `ModifyReseller` | 「Wave for Reseller」ページの編集が可能です。 |
| `ModifyRi` | 「RIの編集」が可能です。 |
| `ModifySettings` | Rippleの環境設定の変更が可能です。 |
| `ReadAccount` | アカウントページを閲覧する権限です。 |
| `ReadBillingGroup` | 請求グループの閲覧権限です。 |
| `ReadInvoice` | 請求書の閲覧権限です。 |
| `ReadInvoiceSettings` | 請求書設定の閲覧権限です。 |
| `ReadRi` | RIの閲覧権限です。 |
| `ReadReseller` | Wave for Resellerページの閲覧権限です。 |



