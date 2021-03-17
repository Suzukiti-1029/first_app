# テーブル設計

## usersテーブル

| Column     | Type   | Option   |
| ---------- | ------ | -------- |
| email      | string | NOT NULL |
| password   | string | NOT NULL |
| name       | string | NOT NULL |
| profile    | text   | NOT NULL |
| occupation | text   | NOT NULL |
| position   | text   | NOT NULL |

### Association

- has_many :prototypes
- has_many :comments

## prototypesテーブル

| Column     | Type       | Option   |
| ---------- | ---------- | -------- |
| title      | string     | NOT NULL |
| catch_copy | text       | NOT NULL |
| concept    | text       | NOT NULL |
| user       | references |          |

### Association

- belongs_to :users
- has_many :comments

※imageカラムはActiveStorageで実装

## commentsテーブル

| Column    | Type       | Option   |
| --------- | ---------- | -------- |
| text      | text       | NOT NULL |
| user      | references |          |
| prototype | references |          |

### Association

- belongs_to :users
- belongs_to :prototypes
