
# Dbdiagram Table
# Gerson Elmer Flores Narciso
table users{
  id int [pk, increment]
  name int [not null]
  email varchar(25) [not null, unique]
  password varchar(25) [not null]
  age int [not null]
  rol int [not null]
}

table course_videos{
  id int [pk , increment]
  title varchar(25) [not null]
  url varchar(25) [not null]
}
table categories {
  id int [pk, increment]
  category varchar(25) [not null]
}
table roles {
  id int [pk , increment]
  rol varchar(25) [not null]
}
table level {
  id int [pk, increment]
  level varchar(25) [not null]
}
table title {
  id int [pk, increment]
  title varchar(25) [not null]
}
table description {
  id int [pk, increment]
  description varchar(50) [not null]
}
table teacher {
  id int [pk, increment]
  teacher varchar(25) [not null]
}
table name {
  id int [pk, increment]
  name varchar(25) [not null]
}
table age {
  id int [pk, increment]
  age int [not null]
}
table course_general{
  id int [pk, increment]
  course_description int [not null]
  course_level int [not null]
  course_teacher int [not null]
  course_user int [not null]
  course_category int [not null]
  course_videos int [not null]
  course_title int [not null]
}

Ref: "level"."id" < "course_general"."course_level"
Ref: "teacher"."id" < "course_general"."course_teacher"
Ref: "title"."id" < "course_general"."course_title"
Ref: "course_videos"."id" < "course_general"."course_videos"
Ref: "categories"."id" < "course_general"."course_category"
Ref: "description"."id" < "course_general"."course_description"

Ref: "users"."id" < "course_general"."course_user"
Ref: "roles"."id" < "users"."rol"

Ref: "name"."id" < "users"."name"

Ref: "age"."id" < "users"."age"