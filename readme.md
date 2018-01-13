# 选课系统

角色:学校、学员、课程、讲师

要求:

1. 创建北京、上海 2 所学校
2. 创建linux , python , go 3个课程 ， linux\py 在北京开， go 在上海开
3. 课程包含，周期，价格，通过学校创建课程
4. 通过学校创建班级， 班级关联课程、讲师
5. 创建学员时，选择学校，关联班级
5. 创建讲师角色时要关联学校，
6. 提供两个角色接口
 1. 学员视图， 可以注册， 交学费， 选择班级，
 2. 讲师视图， 讲师可管理自己的班级， 上课时选择班级， 查看班级学员列表 ， 修改所管理的学员的成绩
 3. 管理视图，创建讲师， 创建班级，创建课程

7. 上面的操作产生的数据都通过pickle序列化保存到文件里

# 文件结构：
```
- lib                  # 启动程序
    - main.py          # 启动入口
- core                 # 核心代码
    - data.py          # 数据的增删改查实现
    - education.py     # 教育有关的5个类，学校，学生，教师，课程，班级
    - school_view.py   # 学校视图
    - student_view.py  # 学生视图
    - teacher_view.py  # 老师视图
- datas                # 数据文件
    - data.pk          # pickle格式的数据文件
- doc                  # 说明文件
```

# 程序缺陷

老师的课程属性，保存的是学生对象，当老师修改学生对象之后，
学生对象的分数值修改了，但是老师的课程属性里边保存的学生对象分数并没有改变
先记下来，后面解决
