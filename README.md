# fastify-prisma-zod-starter
fastify, prisma, zod, swagger, vitest, eslint, prettierを使ったAPIサーバーのスターターテンプレート

ランタイム: node.js （バージョンはHerokuの環境要確認)

バージョン：16以上推奨

※nodeのバージョン管理はvoltaがおすすめ

voltaと他nodeマネージャーの比較 https://cam-inc.co.jp/p/techblog/600182771498877993

voltaの使い方 https://blog.panicblanket.com/archives/6819

言語: typescript

バックエンドフレームワーク: fastify

apiドキュメント: fastify-swagger

ORM: prisma

Request and response validation: fastify-zod

単体テスト： vitest(動かなかったらjest等に変更した方がいいかも)

開発用: ts-node-dev

使い方：
- このリポジトリをforkかcloneする
- npm install

```
npx prisma init --datasource-provider postgresql
```
※postgresqlの場合。上記を実行すると、schema.prismaとDB接続情報の.envが作成されるので、適宜後はお好きに。

- ESLintの設定（お好みで）
```
npm init @eslint/config
```

起動:
npm run dev
ts-node-devが変更を検知してくれるのでファイル変更時のサーバーの再起動は不要です。

### ローカルにDBを作りたい場合：

※事前にDocker Desktopをインストールしておく

1. 適当なディレクトリに以下をclone
```
git clone git@github.com:docodoor-inc/awesome-docker-compose.git
```
2. postgresディレクトリに移動してビルド
```
docker-compose up
```
Docker Desktopで正常に動いていることを確認。

### Prismaの初期化

マイグレーション
```
npx prisma migrate dev --name init
```
上記コマンドを実行すると、schema.prismaファイルに基づいてprisma/migrations配下にmigrationファイルが作成され、マイグレーションするSQLが実行される。

prisma studioの起動:
```
npx prisma studio
```

