# 简易学生选课成绩系统 — 数据库表结构设计

## 1. 学生表（students）

| 字段名 | 数据类型 | 约束 | 说明 |
|---|---|---|---|
| stu_id | VARCHAR(20) | PRIMARY KEY | 学号 |
| name | VARCHAR(50) | NOT NULL | 姓名 |
| gender | CHAR(1) | NOT NULL, CHECK(gender IN ('M','F')) | 性别 |
| birth_date | DATE | | 出生日期 |
| class | VARCHAR(50) | | 班级 |
| email | VARCHAR(100) | UNIQUE | 邮箱 |

```sql
CREATE TABLE students (
    stu_id     VARCHAR(20)  PRIMARY KEY,
    name       VARCHAR(50)  NOT NULL,
    gender     CHAR(1)      NOT NULL CHECK (gender IN ('M', 'F')),
    birth_date DATE,
    class      VARCHAR(50),
    email      VARCHAR(100) UNIQUE
);
```

## 2. 教师表（teachers）

| 字段名 | 数据类型 | 约束 | 说明 |
|---|---|---|---|
| teacher_id | VARCHAR(20) | PRIMARY KEY | 教师编号 |
| name | VARCHAR(50) | NOT NULL | 姓名 |
| department | VARCHAR(100) | NOT NULL | 院系 |

## 3. 课程表（courses）

| 字段名 | 数据类型 | 说明 |
|---|---|---|
| course_id | VARCHAR(20) | 课程号 |
| name | VARCHAR(100) | 课程名 |
| credits | DECIMAL(3,1) | 学分 |
| teacher_id | VARCHAR(20) | 教师编号 |

## 4. 选课成绩表（enrollments）

| 字段名 | 数据类型 | 约束 | 说明 |
|---|---|---|---|
| id | INT | PRIMARY KEY, AUTO_INCREMENT | 自增主键 |
| student_id | VARCHAR(20) | NOT NULL, FK → students(student_id) | 学号 |
| course_id | VARCHAR(20) | NOT NULL, FK → courses(course_id) | 课程号 |
| semester | VARCHAR(20) | NOT NULL | 学期 |
| score | DECIMAL(5,2) | CHECK(score>=0 AND score<=100) | 成绩 |
| — | — | UNIQUE(student_id, course_id, semester) | 防止重复选课 |

```sql
CREATE TABLE enrollments (
    id         INT          PRIMARY KEY AUTO_INCREMENT,
    student_id VARCHAR(20)  NOT NULL,
    course_id  VARCHAR(20)  NOT NULL,
    semester   VARCHAR(20)  NOT NULL,
    score      DECIMAL(5,2) CHECK (score >= 0 AND score <= 100),
    FOREIGN KEY (student_id) REFERENCES students(student_id),
    FOREIGN KEY (course_id)  REFERENCES courses(course_id),
    UNIQUE (student_id, course_id, semester)
);
```
