# テーブル設計

## users テーブル

| Column       | Type   | Options     |
| ----------   | ------ | ----------- |
| nickname         | string | null: false |
| email        | string | null: false |
| password     | string | null: false |
| family_kanji | string | null: false |
| first_kanji  | string | null: false |
| family_kana  | string | null: false |
| first_kana   | string | null: false |
| birthday     | string | null: false |

### Association
- has_many :Products


## items テーブル

| Column      | Type       | Options                        |
| ----------- | ---------- | ------------------------------ |
| item_name   | string     | null: false                    |
| category    | string     | null: false                    |
| price       | integer    | null: false                    |
| seller      | string     | null: false                    |
| message     | text       | null: false                    |
| user        | references | null: false, foreign_key: true |

### Association
- belongs_to :users


## Purchases テーブル

| Column          | Type       | Options                        |
| --------------- | ---------- | ------------------------------ |
| credit_number   | string     | null: false                    |
| expiration_date | integer    | null: false, foreign_key: true |
| security_code   |            | null: false, foreign_key: true |
| user_id         | references | null: false, foreign_key: true |
| product_id      | references | null: false, foreign_key: true |

### Association
- belongs_to :users
- belongs_to :Products

## Addresses テーブル

 Column         | Type       | Options                        |
| ------------- | ---------- | ------------------------------ |
| postal_code   | string     | null: false                    |
| prefecture    | string     | null: false, foreign_key: true |
| city          | string     | null: false, foreign_key: true |
| house_number  | string     | null: false, foreign_key: true |
| building_name | string     | null: false                    |
| tel           |            | null: false, foreign_key: true |

### Association

