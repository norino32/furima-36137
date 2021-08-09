# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

# テーブル設計

## users テーブル(ユーザー情報)

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| password           | string | null: false |

### Association

* has_many :purchase
* has_many :item

## purchases テーブル(購入情報)

| Column | Type           | Options                        |
| ------ | -------------- | ------------------------------ |
| user   | references     | null: false, foreign_key: true |
| item   | references     | null: false, foreign_key: true |

### Association

* belongs_to :user
* belongs_to :item

## items テーブル(商品情報)

| Column              | Type       | Options                        |
| ------------------- | ---------- | ------------------------------ |
| user                | references | null: false, foreign_key: true |
| product_name        | string     | null: false                    |
| description         | text       | null: false                    |
| category_id         | integer    | null: false                    |
| status_id           | integer    | null: false                    |
| burden_id           | integer    | null: false                    |
| delivery_id         | integer    | null: false                    |
| days delivery_id    | integer    | null: false                    |
| price               | integer    | null: false                    |

* belongs_to :user
* has_one :purchase