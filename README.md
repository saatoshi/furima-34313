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
| familyname_kana       | string | null: false               |
| nickname              | string | null: false               | 

### Association

- has_many :items
- has_many :buy_records


## items テーブル

| Column               | Type         | Options            |
| -------------------- | -----------  | -------------------|
| name                 | string       | null: false        |
| item_feature_id      | integer      | null: false        |
| item_category_id     | integer      | null: false        |
| item_used_id         | integer      | null: false        |
| ship_charges_id      | integer      | null: false        |
| adress_area_id       | integer      | null: false        |
| item_cost_id         | integer      | null: false        |
| user                 | references   | foreign_key: true  |

### Association

- belong_to :user
- has_one :buy_record



## get_points テーブル

| Column             | Type       | Options            |
| -----------------  | ---------- | -------------------|
| post_number        | string     | null: false        |
| adress_area_id     | integer    | null: false        |
| adress_city        | string     | null: false        |
| adress_number      | string     | null: false        |
| adress_building    | string     | null: false        |
| phone_number       | string     | null: false        |
| user               | references | foreign_key: true  |

- has_one :buy_record
adress_building


## buy_records テーブル

| Column      | Type       | Options              |
| ----------- | ---------- | ---------------------|
| user        | references | foreign_key: true    |
| item        | references | foreign_key: true    |

### Association

- has_one :item
- belongs_to :user
- has_one :get point