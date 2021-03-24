# README
##テーブル設計

##usersテーブル

| Column     | Type   | Options     |
| -----------| ------ | ----------- |
| email      | string | null: false |
| password   | string | null: false |
| name       | string | null: false |
| occupation | text   | null: false |
| position   | text   | null: false |

### Association

- has_many : prototypesテーブル
- has_many : commentsテーブル

##prototypesテーブル

| Column     | Type       | Options     |
| -----------| ---------- | ----------- |
| title      | string     | null: false |
| catch_copy | text       | null: false |
| concept    | text       | null: false |
| user       | references | foreign_key |

### Association

- belongs_to :usersテーブル
- has_many   :commentsテーブル

##commentsテーブル

| Column     | Type       | Options     |
| -----------| ---------- | ----------- |
| text       | text       | null: false |
| user       | references | foreign_key |
| prototype  | references | foreign_key |

### Association

- belongs_to :usersテーブル
- belongs_to :prototypesテーブル