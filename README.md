#chat-space DB設計
## Userテーブル
| Column | Type | Options |
|-----------|------------|------------|
| name | string | null: false |
| email | string | null: false |
| use_id | integer | null: false,  foreign_key: true |
### Association
- has_many : Message
- has_many : Chat group

## Messageテーブル
| Column | Type | Options |
|-----------|------------|------------|
| body | text |  |
| image | string |  |
| group_id | integer | null: false,  foreign_key: true |
| use_id | integer | null: false,  foreign_key: true |
### Association
- belongs_to : Chat group
- belongs_to : User

## Chat groupテーブル
| Column | Type | Options |
|-----------|------------|------------|
| group_name | string | null: false	 |
| group_id | integer | null: false,  foreign_key: true	 |
| use_id | integer | null: false,  foreign_key: true |
### Association
- belongs_to : User
- has_many : Message

