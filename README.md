# 생활코딩 DATABASE2 MySQL

0. pgAdmin (MySQL 대신 PostgreSQL 쓸거임😎)

1. 테이블 생성

```
CREATE TABLE [테이블 이름] (
    id serial PRIMARY KEY, // primary key는 중복방지용 & MYSQL은 INT(11) NOT NULL AUTO_INCREMENT로 지정해서 1씩 증가하는 값으로 정의함
    title VARCHAR ( 50 ) NOT NULL,
    description TEXT NULL, // 최대 문자길이가 매우큰 값
    created TIMESTAMP NOT NULL,
    author NULL,
    profile NULL
  ); // 마지막에 ;(세미콜론) 필수!
```

2. 테이블 삭제

```
DROP TABLE [테이블 이름];
```

3. CREATE

```
INSERT
  INTO [테이블 이름]
    (title, author, profile, created) // 내가 추가하고 싶은 데이터 key와 NOT NULL값
  VALUES
    ('Hello, Postgre!', 'jack957', '코코', CURRENT_TIMESTAMP);
```

4. READ

```
SELECT id, title, author FROM test 
	WHERE id author='jack957';

SELECT id, title, author FROM test 
	ORDER BY id DESC LIMIT 2;
```

5. UPDATE

```
UPDATE test
	SET title='Delight', author='알랭드보통', profile='왜 나는 너를'
	WHERE id=3; // where 문을 빠뜨리면.. 전부 바뀌어 버리니 매우매우 조심하도록하자..!
```

6. DELETE

```
DELETE FROM test 
  WHERE id = 4; // 마찬가지로 WHERE 문을 빠뜨리지 않도록 조심 또 조심!
``` 

7. JOIN (RDBMS의 꽃!)

```
select * from test2 LEFT JOIN test1 ON test2.author_id = test1.id;

select test2.id as test2_id, title, description, name, profile from test2 left join test1 on test2.author_id = test1.id

```

8. The DB
  - select
  - join
  - index
  - modeling (정규화, 비정규화, etc..)
  - backup (sqldump, binary log, etc...)
  - cloud
  - programming (javascript postgreSQL api, nodeJS postgreSQL api, etc...)