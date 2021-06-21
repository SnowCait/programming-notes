# コードレビュー

## 目的
* コード品質向上
  * バグ発見
  * 保守性向上
* 知識の共有

## 方針
以下の点を重点的に確認する。それ以外はコメントをした上で Approve しちゃう。
* 設計（ユーザーデータであるテーブル設計は最重要）
* バグ
* 保守性

## 確認事項
* 設計
  * 仕様が本当に正しいか
  * テーブルの設計が適切か（データが最重要なので特に注意する、コードは後で直せる）
  * 定義されている箇所が適切か
  * 依存が適切か
* バグ
  * 仕様の要件を満たしているか（＝テストが過不足なく書かれているか）
    * 例外のテストは網羅する
  * 例外のエラーコードが適切か
  * トランザクションが適切か
  * クエリが適切か
    * INDEX効いているか
* 保守性
  * 命名
  * アクセス権
  * 型
  * コードを最小限に保つ
    * そのテーブル/処理は必要か
  * コメントに嘘がないか（コメントが無いのはまだ良いが間違った情報が書かれていることはNG）
  * マジックナンバー
  * 将来的に問題にならないか（メソッドが新規に追加されたら、など）
* その他
  * 不要コメントの削除

## レビューする側

### PR が来たら
1. トリアージ（粒度が適切か、レビュワーが適切か）
1. レビュー工数を見積もってスケジュール
1. レビュー

### 機械がやるべき
* PHPDocが正しいか
* 未使用変数がないか

### コメントするときの配慮
* 直してほしい理由を書く
* なるべく具体的なコードを提案する

## レビューされる側

### プルリクエストを送る際のレビュワーへの配慮
* 1機能1プルリクエスト。なるべく最小になるようにする。
* 実装とリファクタリングはプルリクまたはコミットを分ける（混ざると差分が非常に見づらい）
* 指摘の修正は指摘毎にコミットを分ける
* セルフレビューをする

### テーブル設計
* テーブル設計については事前に相談しておいた方が良い
  * PR を送る段階まで来てしまうと設計ミスがあった場合にコード全体の書き直しになり手戻りが多い

## 参考
- [Google Developers Japan: コードの健全性: 礼儀正しいレビュー == 役立つレビュー](https://developers-jp.googleblog.com/2019/12/respectful-reviews.html)
- [レビューする人も、される人も知っておきたい！開発プロセスごとのレビュー観点チェックリスト - Qiita](https://qiita.com/vankobe/items/551a77fc4fd4b1378fd8)

## メモ

- 問題の指摘
- 意図の確認
- 感想