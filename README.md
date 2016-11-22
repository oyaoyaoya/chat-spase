# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version
 2.3.1

* System dependencies

* Configuration

* Database creation

### モデル-構成

__User-テーブル__

| カラム名    | データ型     | 制約 |
|:-----------|:------------|:-------------|
| nickname   | string      | presence:true|
| email      | string      | uniquences:true|
| passward   | string      |  length: { minimum: 8, maximum: 20 }  |

- has_many: groups
- has_many: groups, through: :group_users

__Group-テーブル__

|  カラム名  |  データ型  |  制約  |
|:-----------|:----------|:-------|
| group_name | strings   | presence: true |


- has_many: messages
- has_many: users, through: :group_users

__GroupUser-テーブル__

|  カラム名  |  データ型  |  制約  |
|:-----------|:----------|:-------|
| group_id | references | foreign_key: true | 
| user_id  | references | foreign_key: true | 

- belongs_to: user
- belongs_to: group

__Message-テーブル__

|  カラム名   |  データ型  |  制約  |
|:-----------|:-----------|:-------|
| group_id    | references | foreign_key: true | 
| user_id　　　| references | foreign_key: true | 
| message_body| text    |  |
| images     |  string   |  |  

- belongs_to: user
- belongs_to: group




* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
