# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version
 2.3.1

* System dependencies

* Configuration

* Database creation

### モデル構成

__Userテーブル__

| カラム名    | データ型     | 制約 |
|:-----------|:------------|:-------------|
| nickname   | string      | presence:true|
| email      | string      | uniquences:true|
| passward   | string      |  length: { minimum: 8, maximum: 20 }  |

- has_many: groups
- has_many: messages, through: groups

__Groupテーブル__

|  カラム名  |  データ型  |  制約  |
|:-----------|:----------|:-------|
| group_name | strings   | presence: true |
| member_id  | references | foreign_key: true | 

- has_many: users
- has_many: messages


__Messageテーブル__

|  カラム名   |  データ型  |  制約  |
|:-----------|:-----------|:-------|
| group_id    | references | foreign_key: true | 
| user_id　　　| references | foreign_key: true | 
| message_body| strings    | presence: true    |

- belongs_to: user
- belongs_to: group

## 分からない所
- [ ] UserテーブルとGroupモデルのリレーション
- [ ] Groupテーブルのmember_idカラムが複数いれる場合の記述



* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
