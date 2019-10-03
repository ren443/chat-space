# README

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user


## messagesテーブル
|column|type|
|------|----|
|body|text|
|image|string|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :group
- belongs_to :user


## usersテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|null: false|
|name|string|null: false|
|email|string|null: false, unipue: true|
|password|string|null: false|
### Association
has_many :messages
has_many :groups_users
has_many :groups, through:  :groups_users

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|id|integer|
|group_name|string|
### Association
has_many :messages
has_many :groups_users
has_many :users, through:  :groups_users





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
