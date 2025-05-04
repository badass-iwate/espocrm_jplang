# espocrm_jplang

EspoCRM 用日本語言語ファイル

## 📁 ディレクトリ構成

EspoCRM を設置したディレクトリの直下に `custom` フォルダを配置し、以下の構成になるようにしてください：

```
/var/www/html/espocrm/custom/
└─ Espo/
└─ Custom/
├─ Resources/
│ ├─ i18n/
│ │ └─ ja_JP/
│ │ ├─ client.json
│ │ └─ admin.json
│ └─ metadata/
│ └─ app/
│ └─ language.json
```

- `client.json`: ユーザーインターフェースの翻訳ファイル  
- `admin.json`: 管理画面の翻訳ファイル  
- `language.json`: EspoCRM にこの言語を認識させるためのメタデータファイル（必須）

---

## 🛠 インストール手順

### 1. 言語ファイルの配置

上記構成で `client.json` と `admin.json` を `ja_JP` フォルダに設置します。

### 2. `language.json` の作成

EspoCRM に `ja_JP` を認識させるために、以下の内容で `custom/Espo/Custom/Resources/metadata/app/language.json` を作成してください：

```json
{
  "list": [
    "__APPEND__",
    "ja_JP"
  ]
}
```

3. キャッシュのクリア
キャッシュをクリアして、新しい言語設定を反映させます。以下のどちらかの方法で実行してください：

管理画面から：
管理 > キャッシュをクリア

コマンドラインから：
EspoCRM インストールディレクトリで次のいずれかのコマンドを実行：

php rebuild.php
または
php command.php clear-cache

4. 言語の選択
キャッシュをクリアした後、以下の場所で日本語が選択可能になります：

管理画面 → 設定 → 言語

各ユーザーのプロフィール設定 → 言語

ここで Japanese (Japan) または 日本語 を選択して保存してください。

📝 補足
client.json: UI 全般のラベルやメッセージを翻訳します。

admin.json: 管理者向け設定画面などの翻訳に対応します。

language.json: EspoCRM がこの言語を「存在する言語」として認識するために必要です。

📚 参考リンク
EspoCRM 公式ドキュメント（翻訳）

EspoCRM GitHub リポジトリ