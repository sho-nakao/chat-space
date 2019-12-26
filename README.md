## userテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|

### Association
- has_many :messages
- has_many :groups_users
- has_many :groups, through: groups_users


## groupテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false| unique: true|

### Association
- has_many :messages
- has_many :groups_users
- has_many :users, through: groups_users


## messageテーブル
|Column|Type|Options|
|------|----|-------|
|text|string|
|image|string
|user_id|string|null: false|foreign_key: true|
|group_id|string|null: false|foreign_key: true|

## Association
- belongs_to :user
- belongs_to :group

## group_userテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|string|null: false|foreign_key: true|
|group_id|string|null: false|foreign_key: true|

## Association
- belongs_to :user
- belongs_to :group
