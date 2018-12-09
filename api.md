# 前后端接口

## 版本记录

| 日期    | 版本 | 修改人      | 备注                       |
| ------- | ---- | ----------- | -------------------------- |
| 18.12.7 | 0.1  | 张怡 徐翔哲 | 增加软工一系统的前后端接口 |
| 18.12.9 | 0.2  | 徐翔哲      | 学生选课接口地址修改       |



## API

### 新建课程

> /api/course  POST

**可能会有异常（选课码重复或课程名重复）**

```json
{
  "name": String,
  "code": String
}

```


>RETURN(normal)

```json
{
  "id"  : number,
  "name": String,
  "code": String
}
```

### 老师查看自己的所有课程（TBD）

> /api/course GET


> RETURN(分页)

```json

[
  {
    "id"  : number,
    "name": String,
    "code": String
  },...
]

```

### 更新课程信息

> /api/course  PUT

```json
{
  "id"  : number,
  "name": String,
  "code": String
}

```

>RETURN(normal) 

**可能会有异常（选课码重复或课程名重复）**

```json
{
  "id"  : number,
  "name": String,
  "code": String
}
```

### 学生选课

> /api/course/student POST

```json
{
  "code": String
}

```

> RETURN(normal)

**可能会有异常（选课码无效）**

```json
{
  "id"  : number,
  "name": String,
  "code": String
}
```

### (在原有的考试API的基础上增加字段)

```json
{
  "course": number(课程id)
}