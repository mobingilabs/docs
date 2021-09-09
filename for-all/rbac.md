# ユーザーの管理

### **機能概要**

Role Based Access Control \(RBAC\) はサブユーザーを作成し、サブユーザーごとに権限を指定できる機能です。

![](../.gitbook/assets/wavetoslackpj-alphausjig-sawjig-sawpng.png)

### **設定方法** <a id="h_c37ca821b1"></a>

1. Wave にログイン
2. Wave 右上に表示されるロゴから「設定」をクリック
3. 左下の「ユーザーの管理」から「ユーザー管理画面を開く」をクリック
4. ユーザー管理画面が別タブで開くので、まずは「ADD ROLE」をクリックし権限を作成
5. 作成した権限をサブユーザー作成時に紐付けることで、サブユーザーに対して任意の権限を付与することができます。

![&#x30ED;&#x30FC;&#x30EB;&#x4F5C;&#x6210;&#x753B;&#x9762;](https://downloads.intercomcdn.com/i/o/246154906/47589e209f6ce4a77687d4e9/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88+2020-09-15+19.00.42.png)

![&#x30B5;&#x30D6;&#x30E6;&#x30FC;&#x30B6;&#x30FC;&#x4F5C;&#x6210;&#x753B;&#x9762;&#x3001;&#x3053;&#x3053;&#x3067;&#x4F5C;&#x6210;&#x3057;&#x305F;&#x6A29;&#x9650;&#x3092;&#x7D10;&#x4ED8;&#x3051;&#x53EF;&#x80FD;](https://downloads.intercomcdn.com/i/o/246156626/525429de1d7dcfa4bd6ad183/%E3%82%B9%E3%82%AF%E3%83%AA%E3%83%BC%E3%83%B3%E3%82%B7%E3%83%A7%E3%83%83%E3%83%88+2020-09-15+19.06.33.png)

#### **ロールの各項目一覧** <a id="h_1fcb1e8f4a"></a>

Wave - Waveに関連する権限

User - ユーザー管理画面で Waveアカウント/ユーザー作成、閲覧、編集する権限

Role - ユーザー管理画面で権限を作成、閲覧、編集する権限

#### Wave 配下の各権限の説明 <a id="h_99e543c45a"></a>

| Action | 解説 |
| :--- | :--- |
| Admin | 全ページ閲覧、編集可能な管理者権限 |
| Account \(ready only\) | 選択されたアカウントのみ参照可能 |
| Account settings - Read & Write Access | アカウント名称や予算設定機能の編集が可能 |
| Account settings - Read Only | アカウント名称等の参照権限 |
| Download bulk | 一括ダウンロードCSVの有効化 |
| Group - Read & Write Access | グループの作成や編集権限 |
| Group - Read Only | グループの参照権限 |
| Ri \(read only\) | 所有している RI の参照権限 |
| Settings - Read & Write Access | アカウントの設定（言語変更、パスワード変更、2段階認証など）の変更権限 |
| Settings - Read Only | アカウントの設定（言語変更、パスワード変更、2段階認証など）の参照権限 |
| Tags - Read & Write Access | コスト配分タグの編集権限 |
| Tags - Read Only | コスト配分タグの参照権限 |

