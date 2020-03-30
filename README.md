# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

# DB設計

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|text|null: false, indx: true|
|email|string|null: false, unique: true|
### Association
has_many :messages
has_many :groups_users
has_many :groups, through: :groups_users

## messagesテーブル
|Column|Type|Options|
|------|----|-------|
|text|string||
|image|string||
|user_id|integer|null: false, foreign_key: user_id|
|group_id|integer|null: false, foreign_key: group_id|
### Association
belongs_to :user
belongs_to :group


## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
has_many :messages
has_many :groups_users
has_many :users, through: :groups_users


## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|groups_id|integer|null: false, foreign_key: true|
|users_id|integer|null: false, foreign_key: true|
### Association
belongs_to :group
belongs_to :user

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
