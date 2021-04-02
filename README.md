# Week5

1.建立單筆資料
insert into user (name, username, password) values
('user1', 'ply', 'ply');
![image](https://github.com/ChenYee-Wang/Week5/blob/main/1.png)'

2.建立多筆資料
insert into user (name, username, password) values
('user2', 'Tom', 'Abc'),
('user3', 'Jenny', 'Def'),
('user4', 'Zac', 'Ghi'),
('user5', 'Peggy', 'Jkf');
![image](https://github.com/ChenYee-Wang/Week5/blob/main/2.png)

3.取得user中所有資料
select * from user;
![image](https://github.com/ChenYee-Wang/Week5/blob/main/3.png)

4.取得資料總數
select count(*) from user;
![image](https://github.com/ChenYee-Wang/Week5/blob/main/4.png)

5.取得use中的使用者資料，並按照 time 欄位，由近到遠排序
select * from user order by time desc;
![image](https://github.com/ChenYee-Wang/Week5/blob/main/5.png)

6.取得第2~4筆資料，並按照 time 欄位，由近到遠排序
select * from user order by time desc,id limit 1, 3;
![image](https://github.com/ChenYee-Wang/Week5/blob/main/6.png)

7.取得欄位username是ply的資料
select * from user where username='ply';
![image](https://github.com/ChenYee-Wang/Week5/blob/main/7.png)

8.取得欄位username且欄位password也是ply的資料
select * from user where username='ply' and password='ply';
![image](https://github.com/ChenYee-Wang/Week5/blob/main/8.png)

9.更新username是ply的資料，將name欄位改成【丁滿】
update user set name='丁滿' where username='ply';
![image](https://github.com/ChenYee-Wang/Week5/blob/main/9.png)

10.使用 DELETE 指令刪除所有在資料表中的資料
delete from user;
![image](https://github.com/ChenYee-Wang/Week5/blob/main/10.png)

---------------------------------------------------------------------------

製作message資料表
create table message (
id bigint auto_increment current '獨立編號',
user_id bigint not null comment '留言會員編號',
content varchar(255) not null comment '留言內容',
time datetime default now() comment '留言時間',
primary key (id),
foreign key (user_id) references user(id)
);
![image](https://github.com/ChenYee-Wang/Week5/blob/main/額外題1.png)

加入留言
insert into message (user_id, content) values
('1', '這遊戲太好玩啦，我把房子賣了現在在公園玩'),
('2', '輸入TK888，就送魔關羽'),
('3', '頂天立地，上山下海');
![image](https://github.com/ChenYee-Wang/Week5/blob/main/額外題2.png)

取得所有留言，包含會員姓名
select username, content
from user
inner join message
on user.id=message.id;
![image](https://github.com/ChenYee-Wang/Week5/blob/main/額外題3.png)

取得username是ply的所有留言
select username, content
from user
inner join message
on user.id=message.id
where username='ply';
![image](https://github.com/ChenYee-Wang/Week5/blob/main/14.png)
