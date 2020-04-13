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

## usersテーブル

|Column|Type|Options|
|--------|-----|------|
|email|string|null:false|
|nickname|string|null: false, index: true|
|password|string|null:false|
###Association
- has_many :posts
- has_many :groups,  through:  :groups_users
- has_many :groups_users

##Postsテーブル
|Column|Type|Options|
|--------|-----|------|
|image|string||
|text|text||
|user|referenes|null:false, foreign_key: true|
|post|referenes|null:false, foreign_key: true|
###Association
- belongs_to :user
- belongs_to :group

##Groupsテーブル
|Column|Type|Options|
|--------|-----|------|
|name|string|null:false|
###Association
- has_many :users, through:  :groups_users
- has_many :groups_users
- has_many :posts

##Groups_usersテーブル
|Column|Type|Options|
|--------|-----|------|
|user|referenes|null: false, foreign_key: true|
|group|referenes|null: false, foreign_key: true|
###Association
- belongs_to :group
- belongs_to :user