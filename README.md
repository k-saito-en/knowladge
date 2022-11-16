# knowladge
調べた、習得した、教えてもらった知識をここに貯蔵していきます。

# 認証・セキュリティ

## OpenID Connect
- [一番分かりやすい OpenID Connect の説明](https://qiita.com/TakahikoKawasaki/items/498ca08bbfcc341691fe) 2017/07

### OAuth 2.0

- [一番分かりやすいOAuthの説明](https://qiita.com/TakahikoKawasaki/items/e37caf50776e00e733be) 2017/07
- [OAuth2.0の流れをまとめてみる](https://zenn.dev/mryhryki/articles/2020-12-28-oauth2-flow) 2021/04

  ![IMG_1AAD0A063342-1](https://user-images.githubusercontent.com/111550856/202054210-50bbc9a4-e94c-4344-a0bf-7f834b896127.jpeg)

- アクセストークン：認可（リソースへのアクセスコントロール＝あるリソースへの権限（readやwriteなど）を持っているかどうか確認すること）
- IDトークン：認証（その人が誰かを確認すること）

### クエリパラメータ
- サーバーに情報を送るためにURLの末尾につけ足す文字列（変数）
- [クエリ文字列（URLパラメーター）とは？Webサービス上の用途とその役割](https://online.dhw.co.jp/kuritama/query-string/amp/) 2020/10

## トークン

### GCP関連
- https://developers.google.com/identity/protocols/oauth2?hl=ja
- https://blog.shinonome.io/google-api/amp/

これが1番分かりやすかった↓
- https://qiita.com/hanzawak/items/7355142f884cb56a4d57
  - リフレッシュトークンを用いる
  - パブリッククラウドの認証を用いる
    - https://christina04.hatenablog.com/entry/secure-token-management
    - Googleauthを利用した簡略化された手続きが存在する？
      - https://dev.classmethod.jp/articles/oauth2client-is-deprecated/
- revoke
  - 一回使ったアクセストークンを無効にする作業
  - Slack bolt側での設定
    - https://qiita.com/seratch/items/610c14208772d49ac9e4
- Googleログイン実装
  - https://firebase.google.com/docs/auth?hl=ja
  - ユーザーアカウントでのログインが必須？
  - 権限付与+自身での確認
