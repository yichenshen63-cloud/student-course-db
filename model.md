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

