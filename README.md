## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user


## usersテーブル

|Column|Type|Options|
|------|----|-------|
|nickname|string|add_index: true, null: false|
|email|string|null: false, unique: true|
|password|string|null: false|
|password_confirmation|string|null:false|

### Association
- has_many :groups_users
- has_many :groups, through:  :groups_users
- has_many :messeges

## groupsテーブル

|Column|Type|Options|
|------|----|-------|
|group_name|string|null: false, unique: true|

### Association
- has_many :users, through:  :group_users
- has_many :group_users
- has_many :messages
## messagesテーブル

|Culumn|Type|Option|
|------|----|------|
|image|string|
|body|text|
|group_id|integer|null: false,foreign_key: true|
|user_id|integer|null: false,foreign_key: true|

### Association
- belongs_to user
- belongs_to group



