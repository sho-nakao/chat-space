## userテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|

### Association
- has_many :message
- has_many :group_user
- has_many :group, through: group_user


## groupテーブル
|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false| unique: true|

### Association
- has_many :message
- has_many :group_user
- has_many :user, through: group_user


## messageテーブル
|Column|Type|Options|
|------|----|-------|
|text|string|null: false|
|image|string|null: false|
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
