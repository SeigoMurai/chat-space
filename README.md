# README

# chat-space DB設計図
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false|
|password|string|null: false|
|nickname|string|null: false|
### Association
- has_many :tweets
- has_many :messages

## groupテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false|
|memmber|string|null: false|
|user_id|integer|null: false, foreign_key: true|
### Association
- has_many :users
- has_many :messages
- has_many :users_groups

# users_groupsテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group

# messageテーブル
|Column|Type|Options|
|------|----|-------|
|image|text||
|text|text||
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :group