# テーブル設計

## users テーブル

| Column                | Type   | Options                   |
| -----------------     | ------ | -----------------------   |
| birsthday             | date   | null: false               |
| email                 | string | null: false, unique: true |
| encrypted_password    | string | null: false, default: ""  |  
| firstname             | string | null: false               |
| familyname            | string | null: false               |
| firstname_kana        | string | null: false               |
| familyname_kana       | text   | null: false               |
| nickname              | text   | null: false               | 

### Association

- has_many :items
- has_many :buy_records


## items テーブル

| Column               | Type         | Options     |
| -------------------- | -----------  | ----------- |
| image                |              |             |
| name                 | string       | null: false |
| item_feature_id      | intege       | null: false |
| item_category_id     | intege       | null: false |
| item_used_id         | intege       | null: false |
| ship_charges_id      | intege       | null: false |
| shipper_erea_id      | intege       | null: false |
| item_cost            | string       | null: false |
| user                 | references   |             |

### Association

- belong_to :user
- has_one :buy_record



## get_points テーブル

| Column             | Type       | Options     |
| -----------------  | ---------- | ------------|
| post_number        | string     | null: false |
| adress_area        | string     | null: false |
| adress_city        | string     | null: false |
| adress_number      | string     | null: false |
| phone_number       | string     | null: false |
| users_id           | text       | null: false |




## buy_records テーブル

| Column      | Type       | Options     |
| ----------- | ---------- | ------------|
| custome     | text       | null: false |
| user        | references |             |
| item        | references |             |

### Association

- has_one :item
- belongs_to :user