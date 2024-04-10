# テーブル設計

## users テーブル

| Column             | Type   | Options                   |
| ------------------ | ------ | ------------------------- |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |
| name               | string | null: false               |
| profile            | text   | null: false               |
| occupation         | text   | null: false               |
| position           | text   | null: false               |

### Association

 - has many :prototypes
 - has many :comments

## prototypes テーブル
| Column     | Type       | Options                  |
| ---------- | ---------- | ------------------------ |
| title      | string     | null: false              |
| catch_copy | text       | null: false              |
| concept    | text       | null: false              |
| user       | references | null: false, foreign_key |

### Association
 - belongs_to :user
 - has many :comments
  
## comments テーブル
| Column    | Type       | Options                  |
| --------- | ---------- | ------------------------ |
| content   | text       | null: false              |
| prototype | referencest       | null: false, foreign_key |
| user      | references | null: false, foreign_key |

### Association
 - belongs_to :user
 - belongs_to :prototype