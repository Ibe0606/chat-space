#chat-space DB設計
## usersテーブル
| Column | Type | Options |
|-----------|------------|------------|
| name | string | null: false, index: true |
### Association
- has_many : messages
- has_many : groups

## messagesテーブル
| Column | Type | Options |
|-----------|------------|------------|
| body | text |  |
| image | string |  |
| group_id | integer | null: false,  foreign_key: true |
| use_id | integer | null: false,  foreign_key: true |
### Association
- belongs_to :group
- belongs_to :user

## groupsテーブル
| Column | Type | Options |
|-----------|------------|------------|
| name | string | null: false	 |
### Association
- has_many :users, through: :members
- has_many :members
- has_many :messages
