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

##Users テーブル

|Columun|Type|Option|
|-------|----|------|
|email|string|null: false|
|nickname|string|null: false|
|password|string|null: false|

###Association
- has_many :posts
- has_many :groups, through: :groups_users

##Posts

|Columun|Type|Option|
|-------|----|------|
|text|text|null: false|
|user_id|integer|null:false, foreign_key: true|

###Association
- belongs_to :user
- belongs_to :group

##Groups
|Columun|Type|Option|
|-------|----|------|
|name|string|null: false|
|user_id|string|null: false, foreign_key: true|
|post_id|string|null: false, foreign_key: true|

###Association
has_many :users, through: :groups/user
has_many :posts

##groups_user
Columun|Type|Option|
|-------|----|------|
|user_id|string|null: false, foreign_key: true|
|group_id|string|null: false, foreign_key: true|

###Association
- belongs_to :user
- belongs_to :group