CONTRIBUTING to gitlab-i18n-patch
=================================

## 翻訳追加/修正の手順

翻訳追加/修正は以下の手順で行っています。

### v6.6.4-v8.2.x

今後は旧来の手順での更新をやめ、 作成済みのパッチに対する誤字脱字の修正のみを実施するつもりです。

patchesディレクトリ以下の.patchファイルを更新してプルリクエストしてください。

### v8.3.0以降

GitLab v8.3.0 以降については、基本的に i18n-patch を使ったパッチ作成を進めていきます。

以下の手順で作成・更新してください。

1. [yarn](https://github.com/yarnpkg/yarn) をインストール (初回のみ)
1. node/npm をインストール (初回のみ)
1. `yarn` を実行
1. `config/i18n.yml`, `config/ja.yml` を更新
1. 対象バージョンを増やすときは `config/gitlab.yml` を更新
1. `npm run translate` で対象全バージョンのパッチを更新
1. 対象となるVagrantのVMを起動 (必須ではない)
    * 英語と日本語の長さの差でデザインが崩れたり、翻訳の不備によりシンタックスエラーなどが発生したりする恐れがある場合は動作確認します。
    * 例) `vagrant up v830`
1. 起動したVMを使って動作確認
1. コミットしてプルリクエスト送信

### (参考)未作成パッチの確認

`npm run check` を実行すると、リリースされているバージョンのうちまだパッチが作られていないものを確認できます。  
`npm run update` を実行すると、リリースされているバージョンのうちまだパッチが作られていないものを`config/gitlab.yml`に追加します。
