\# 简易学生选课成绩系统 — 数据库表结构设计



\## 1. 学生表（students）



| 字段名 | 数据类型 | 约束 | 说明 |

|---|---|---|---|

| stu\_id | VARCHAR(20) | PRIMARY KEY | 学号 |

| name | VARCHAR(50) | NOT NULL | 姓名 |

| gender | CHAR(1) | NOT NULL, CHECK(gender IN ('M','F')) | 性别 |

| birth\_date | DATE | | 出生日期 |

| class | VARCHAR(50) | | 班级 |

| email | VARCHAR(100) | UNIQUE | 邮箱 |



```sql

CREATE TABLE students (

&#x20;   stu\_id     VARCHAR(20)  PRIMARY KEY,

&#x20;   name       VARCHAR(50)  NOT NULL,

&#x20;   gender     CHAR(1)      NOT NULL CHECK (gender IN ('M', 'F')),

&#x20;   birth\_date DATE,

&#x20;   class      VARCHAR(50),

&#x20;   email      VARCHAR(100) UNIQUE

);

```

\## 2. 教师表（teachers）



| 字段名 | 数据类型 | 约束 | 说明 |

|---|---|---|---|

| teacher\_id | VARCHAR(20) | PRIMARY KEY | 教师编号 |

| name | VARCHAR(50) | NOT NULL | 姓名 |

| department | VARCHAR(100) | NOT NULL | 院系 |



\## 3. 课程表（courses）



| 字段名 | 数据类型 | 说明 |

|---|---|---|

| course\_id | VARCHAR(20) | 课程号 |

| name | VARCHAR(100) | 课程名 |

| credits | DECIMAL(3,1) | 学分 |

| teacher\_id | VARCHAR(20) | 教师编号 |



\## 4. 选课成绩表（enrollments）



| 字段名 | 数据类型 | 说明 |

|---|---|---|

| id | INT | 主键 |

| student\_id | VARCHAR(20) | 学号 |

| course\_id | VARCHAR(20) | 课程号 |

| score | DECIMAL(5,2) | 成绩 |



