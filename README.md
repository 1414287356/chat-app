# テーブル設計

 ## users テーブル

| Columu  | Type   | Options     |
| ------- | ------ | ----------- |
| name    | string | null: false |
| email   | string | null: false |
| password| string | null: false |

### Association

_ has_many :room_users
_ has_many :rooms, through: rooms_users
_ has_many :messages

## rooms テーブル

| Columu  | Type   | Options     |
| ------- | ------ | ----------- |
| name    | string | null: false |

### Association

_ has_many :room_users
_ has_many :rooms, through: rooms_users
_ has_many :messages

## room_users テーブル

| Columu  | Type      | Options                        |
| ------- | --------- | ------------------------------ |
| user    | refrences | null: false, foreign_key: true |
| room    | refrences | null: false, foreign_key: true |

### Association

_ belongs_to :room
_ belongs_to :user

## messages テーブル

| Columu  | Type      | Options                        |
| ------- | --------- | ------------------------------ |
| content | string    |                                |
| user    | refrences | null: false, foreign_key: true |
| room    | refrences | null: false, foreign_key: true |

### Association

_ belongs_to :room
_ belongs_to :user
