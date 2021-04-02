# kokura-web
## 環境構築手順
- kokura-web直下に`.env`ファイル作成してください
    - `.env`のアクセス用IDは他のエンジニアに聞いてください
    - 鍵情報も含まれるため、取り扱いには注意してください

- `npm install` でpackege.jsonを読み込んでください。

Node の version はv14 系の安定版を使用してください。

```bash
bash
$ node -v
v14.15.4
```

## **anyenv推奨**

- Nodeのversionを自動管理してくれるためのツールです。

    [anyenv/anyenv](https://github.com/anyenv/anyenv)

## install手順

```bash
bash
$ brew install anyenv
$ anyenv init
```

使ってるシェルの設定ファイルに追記するようにと、指示が出るのでそのとおりに従う。

※シェルの再起動が必要(ターミナルを開き直すでもいいです)

```bash
exec $SHELL -l
```

マニフェストディレクトリがないと怒られる場合は、以下のコマンドで initialize する。

```bash
bash
$ anyenv install --init
```

**### nodenv install**

anyenv を使って nodenv をインストールする。

```bash
bash
$ anyenv install nodenv
$ exec $SHELL -l
```

※\$SHELL がないって怒られる場合(fish)はシェル再起動か設定ファイルを再ロードしてください.

**### Node.js install**

```bash
bash
$ nodenv install 14.15.4
$ nodenv global 14.15.4
$ exec $SHELL -l
```

### **ローカルサーバー**

`$ npm start` 

**Gatsby develop**

`$ npm run develop`

### **Storybook**

`$ npm run develop-sb`

### **linter**

#### eslintのみ 
`$ npm run eslint` 
#### stylelintのみ 
`$ npm run stylelint` 

#### 同時 
`$ npm run lint`

上記以外の script は`package.json`を参照のこと

### **※注意**

- `$ npm audit fix` で脆弱性を修正しようとすると、開発環境にerrrorがでます。
- gatsby-source-contentful-v5.2.0に上げて脆弱性を修復しようとしますが、同時にgatsby-v3のupdateが必要になります。gatsbyが2021/3月に-v3にupdateされましたが、-v3以降の対応が現状(2021/4/2)できていません。
- gatsby-source-contentful以外にHighな脆弱性が見つからないため開発環境では-v4~で開発を進めています。
- gatsby-v3系の移行完了次第、この注意書きを消してください。

[Migrating from v2 to v3](https://www.gatsbyjs.com/docs/reference/release-notes/migrating-from-v2-to-v3/)
