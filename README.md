# テーブル設計

## users テーブル

| Column           | Type   | Options     |
| ---------------- | ------ | ----------- |
| email            | string | null: false |
| password         | string | null: false |
| nickname         | string | null: false |

## Association

- has_many :tweets
- has_many  :

## tweets テーブル

| Column            | Type       | Options                        |
| ----------------- | ---------- | ------------------------------ |
| name              | string     | null: false                    |
| price             | integer    | null: false                    |
| information       | text       | null: false                    |
| status_id         | integer    | null: false                    |
| delivery_fee_id   | integer    | null: false                    |
| area_id           | integer    | null: false                    |
| category_id       | integer    | null: false                    |
| shipping_date_id  | integer    | null: false                    |
| user              | references | null: false, foreign_key: true |


## Association

- has_many :comments
- belong_to :user

## comments テーブル

| Column         | Type       | Options                        |
| -------------- | ---------- | ------------------------------ |
| user           | references | null: false, foreign_key: true |
| item           | references | null: false, foreign_key: true |

## Association

- belong_to :user
- belong_to :item
- has_one :address

## Like テーブル

| Column         | Type       | Options                        |
| -------------- | ---------- | ------------------------------ |
| post_code      | string     | null: false                    |
| city           | string     | null: false                    |
| address        | string     | null: false                    |
| building       | string     |                                |
| phone_number   | string     | null: false                    |
| area_id        | integer    | null: false                    |
| order          | references | null: false, foreign_key: true |
### Association

- belongs_to :order
