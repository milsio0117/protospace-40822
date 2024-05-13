# README

## users

| Column             | Type    | Options     | 
| -------------------| --------| ----------- | 
| profile            | text    | null:false  | 
| name               | string  | null:false  | 
| encrypted_password | string  | null:false  | 
| email              | string  | null:false, unique: true | 
| occupation         | text    | null:false  | 
| positioin          | text    | null:false  | 

has_many: comments
has_many: properties



## prototypes

| Column      | Type        | Options     | 
| ------------| ------------| ----------- | 
| title       | string      | null:false  | 
| catch_copy  | text        | null:false  | 
| concept     | text        | null:false  | 
| user        | references  | null:false, foreign_key:true | 

belongs_to :user
has_many :comments


## comments

| Column    | Type        | Options     | 
| ----------| ------------| ----------- | 
| content   | text        | null:false  | 
| prototype | references  | null:false, foreign_key:true | 
| user      | references  | null:false, foreign_key:true | 

belongs_to :user
belongs_to :prototype