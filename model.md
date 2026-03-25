\# 简易学生选课成绩系统 — 数据库表结构设计



\## 1. 学生表（students）



| 字段名 | 数据类型 | 约束 | 说明 |

|---|---|---|---|

| stu\_id | VARCHAR(20) | PRIMARY KEY | 学号 |

| name | VARCHAR(50) | NOT NULL | 姓名 |

| gender | VARCHAR(10) | NOT NULL | 性别 |

| email | VARCHAR(100) | UNIQUE | 邮箱 |



\## 2. 教师表（teachers）



| 字段名 | 数据类型 | 约束 | 说明 |

|---|---|---|---|

| teacher\_id | VARCHAR(20) | PRIMARY KEY | 教师编号 |

| name | VARCHAR(50) | NOT NULL | 姓名 |

| department | VARCHAR(100) | NOT NULL | 院系 |

