# openpyxl-pandas練習用課題
- 100本ノックの第1章で扱うcsvデータ(以下参照)をsrcディレクトリ内に入れる
  - `customer_master.csv`
  - `item_master.csv`
  - `transaction_1.csv`
  - `transaction_2.csv`
  - `transaction_detail_1.csv`
  - `transaction_detail_2.csv`

- 100本ノックでやった通り、`transaction`系のデータはファイルが分かれているため、1つにユニオンしてから扱うこと


# 要件
- 指定した条件に当てはまる顧客の請求書を自動作成するプログラム
- `./bill_format.xlsx`を基に、顧客1人につき1つの請求書ファイルを作成すること
- 作成した請求書ファイルは、`./bills/`ディレクトリに格納すること
- 請求書を作成する対象の顧客を、以下の条件でフィルタできるようにすること(※条件の入力方法は問わない)
  - 出身県（ex: 神奈川県）
  - 年齢帯（ex: 20代）
  - 性別（ex: 男性）

- 作成した請求書のファイル名は「`〇〇様ご請求書.xlsx`」（〇〇は顧客名）という形式にすること
- `A2`セルには顧客のフルネームを「`名字 氏名 様`」という形式で入力すること
- `E2`セルにはプログラムを実行した日付を「`2023/06/12`」という形式で入力すること
- `B5`セルには件名を「`〇〇様ご購入分請求`」という形式で入力すること
- `B6`セルには請求日の1週間後の日付を「`2023/06/19`」という形式で入力すること
- `B9`セルには合計金額（税込み）を「`10,000円（税込み）`」という形式で入力すること
- 12~19行目には、対象の顧客が購入した商品情報とその金額を入力すること
- `E21`セルには、算出した小計の10%の値を消費税として入力すること


# 実装の流れ
1. pandasで各csvを読み込む
2. 顧客ごとの購入情報が必要な形式で抽出できるように整形する
3. 指定された条件でフィルターされた顧客の請求書を作成する

