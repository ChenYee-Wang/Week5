# Week5

建立單筆資料
insert into user (name, username, password) values
('user1', 'ply', 'ply');

建立多筆資料
insert into user values
('user2', 'Tom', 'Abc'),
('user3', 'Jenny', 'Def'),
('user4', 'Zac', 'Ghi'),
('user5', 'Peggy', 'Jkf');

取得user中所有資料
select * from user;

取得資料總數
select count(*) from user;

取得use中的使用者資料，並按照 time 欄位，由近到遠排序
select * from user order by time desc;

取得第2~4筆資料，並按照 time 欄位，由近到遠排序
select * from user where id between 2 and 4 order by time desc;

取得欄位username是ply的資料
select * from user where username='ply';

取得欄位username且欄位password也是ply的資料
select * from user where username='ply' and password='ply';

更新username是ply的資料，將name欄位改成【丁滿】
update user set name='丁滿' where username='ply';

使用 DELETE 指令刪除所有在資料表中的資料
delete from user;
