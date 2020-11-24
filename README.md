# README

## users テーブル

| Column    | Type   | Options  |
| --------- | ------ | -------- |
| name      | string | not null |
| email     | string | not null |
| password  | string | not null |
| profile   | text   | not null |
| occupation| text   | not null |
| position  | text   | not null |

### Association

- has_many :prototypes
- has_many :comments

## prototypes テーブル

| Column     | Type       | Options  |
| ---------- | ---------- | -------- |
| title      | string     | not null |
| catch_copy | text       | not null |
| concept    | text       | not null |
| user       | references | not null |

### Association

- has_many   :comments
- belongs_to :users

## comments テーブル

| Column      | Type       | Options  |
| ----------  | ---------- | -------- |
| text        | text       | not null |
| user        | references |          |
| prototype   | references |          |

### Association

- belongs_to :users
- belongs_to :prototypes
