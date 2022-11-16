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

# Python

## 仮想環境
### なぜ使うのか
- 開発プロジェクトによってモジュールを使い分けたい時
- バージョンによって使い分けを行いたい時
- 違うPCでも開発したり、複数人のチームで開発したりする時は、どこでも同じ仮想環境を使うようにする必要がある

### venvモジュール
- https://docs.python.org/ja/3/library/venv.html


## PowerShell
- Windowsで権限の強いコマンドを使用する時に用いる

## 文法
### 辞書
- get(key)で値を取り出せる
- items()でkeyとvalueの組を総ざらいすることも可能
### with文 
- Javaで言うFinally
- 絶対に処理して欲しい内容を記述
- その処理毎に書く
### open文
- ファイルの読み込み（モード指定有）
### 文字コードの指定
- エンコードの違いから明示が必要
### for文
- inのあとはiterという関数が組み込まれている
    - イテレータに変換する関数
    - Javaのプリントメソッドにもこんなんなかったっけ？
    - リストはイテレータではないが、イテラブル（iterが適用できるオブジェクト）
        - rangeが返すオブジェクト
- enumerate()
    - forループの中でリストやタプルなどのイテラブルオブジェクトの要素と同時にインデックス番号（カウント、順番）を取得できる。
### import文
- ワイルドカードで無差別にimportできる
- asで名称を再定義できる

### equals

- https://blog.tiqwab.com/2017/02/26/implement-eq-in-python.html  5年前の更新につき注意
- is
    - 同一性を判定
- ==
  - __lt__	Less Than：未満
  - __le__	Less Than or Equal：以下
  - __eq__	Equal：同じ
  - （__ne__	Not Equal：違う）
  - __gt__	Greater Than：より大きい
  - __ge__	Greater Than or Equal：以上
          - 比較演算の定義、実装
          - 引数を2つ受け取り、比較
### 関数=メソッド
- def文
- 返値
    - return文で定義
- 引数
    - 順番
        - 位置引数, 初期値を持つ引数, 可変長引数, 辞書型の可変長引数
    - キーワード引数
        - 引数単体で辞書型のような実装を持つことが出来る
    - 初期値
        - コンストラクタのような実装を持つことができる
    - 可変長引数
        - 辞書型
- 約束事
- 1つの関数につき、1タスクに留めるべき
### 変数
- グローバル変数
    - 関数の中で代入が行われない変数は全てグローバル変数とみなされる
- ローカル変数
    - 関数内でのみ利用可能
    - グローバル変数と同名の変数を定義すると、ローカル変数になる
### 例外処理まわり
- assert文
    - Trueを返すべきブロックを監視
### フォーマット済み文字リテラル
- 文字列の頭に f か F を付け、式を {expression} と書くことで、 Python の式の値を文字列の中に入れ込めます。
    - https://docs.python.org/ja/3/tutorial/inputoutput.html#tut-f-strings


## 継承
- 引数にスーパークラスを持ってくることで単一継承できる
## class
- Javaのようにクラスを定義できる
    - アクセス権限付与のため？
        - 変数の前に_、__をつけてアクセス制限
    - 継承、オーバーライド、ポリモーフィズムを実現するために関数と分けてclassがある
- 主に、データとデータを操作する方法をまとめるhttps://snowtree-injune.com/2019/02/11/python-class-necessity/#toc2
- __init__
    - コンストラクタ
        - インスタンス作成時の初期設定
        - コンストラクタの関数名に定義
        - 例：インスタンス化時に名前フィールドを初期化https://magazine.techacademy.jp/magazine/24530
- __del__
    - デストラクタ
        - インスタンス削除時に呼び出される
## json
- データに意味付けをする
- https://niwakomablog.com/python-how2use-json-dump-and-dumps/
- 書き込む時は
    - dump()
        - 辞書をjsonファイルとして変換
    - dumps()
        - 辞書をjson形式の文字列に変換



 .ipynb
    * 対話形式の実行内容も保存する
    * コードセルだけ取込むことも可能


## モジュール
ファイルの単位としてモジュールが使用される
- osモジュール
    - pass周りの設定を行う
    - タイムスタンプの取得

## パッケージ
Javaと異なり、ディレクトリの単位として用いられる

## ライブラリ
### NumPy
- 多次元配列を扱うライブラリ
- 標準ライブラリでは無い（import）
    - array
        - 配列の構築
        - データ型はndarrayの特殊型

## ファイル拡張子
### .ipynb
- 対話形式の実行内容も保存する
- コードセルだけ取込むことも可能
