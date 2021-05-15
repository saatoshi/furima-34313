# テーブル設計

## users テーブル

| Column            | Type   | Options     |
| --------          | ------ | ----------- |
| birsthday         | string | null: false |
| email             | string | null: false |
| password          | string | null: false |
| firstname         | string | null: false |
| familyname        | text   | null: false |
| firstname_kana    | text   | null: false |
| familyname_kana   | text   | null: false |

### Association

- has_many :items
- has_one :get_point
- has_many :buy_records


## items テーブル

| Column            | Type         | Options     |
| --------          | ------       | ----------- |
| image             |              |             |
| item_name         | string       | null: false |
| item_feature      | text         | null: false |
| item_category     | text         | null: false |
| item_used         | text         | null: false |
| ship_charges      | text         | null: false |
| shipper_erea      | string       | null: false |
| item_cost         | string       | null: false |
| owner             | text         | null: false |
| user              | references   |             |

### Association

- belong_to :user
- has_one :buy_record



## get_points テーブル

| Column             | Type       | Options     |
| ------             | ---------- | ------------|
| post_number        | string     | null: false |
| adress_area        | string     | null: false |
| adress_city        | text       | null: false |
| adress_number      | text       | null: false |
| phone_number       | string     | null: false |
| users_id           | text       | null: false |


### Association

- belongs_to :user


## buy_records テーブル

| Column      | Type       | Options     |
| ------      | ---------- | ------------|
| custome     | text       | null: false |
| user        | references |             |
| item        | references |             |

### Association

- has_one :item
- belongs_to :user