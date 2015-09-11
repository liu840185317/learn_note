## MySQL Basic Command


#### Connect MySQL
`mysql -h主机地址 -u用户名 －p用户密码`
*PS :* 如果为本地连接可取消`-h主机地址`参数

#### Change user's password
- Rember old password
    `mysqladmin -u 用户名 -p 旧密码 password 新密码`
- Forgot old password
    ```bash
    # Frist : 使用root用户登录
    use mysql;

    UPDATE user SET password=PASSWORD("new password") WHERE user='username';
    # or SET PASSWORD FOR   username=PASSWORD('new password');
    ```

####Show table's message
- Show columns
    `DESC table_name`
- Show all message
    `SHOW CREATE TABLE table_name`

####ALTER TABLE：添加，修改，删除表的列
- Change table_name
    `ALTER TABLE old_name RENAME TO new_name`
- Add column
    `ALTER TABLE table_name ADD COLUMN column_name data_type `
- Delete column
    `ALTER TABLE table_name DROP COLUMN column_name`
- Rename coulumn_name
    `ALTER TABLE table_name CHANGE old_name new_name data_type `


#### 备份数据库
- 导出整个数据库(导出文件默认是存在mysql\bin目录下)
    `mysqldump -h主机地址 -u用户名 -p密码 数据库名 > filepath/filename.sql`

- 导出一个表
    `mysqldump -h主机地址 -u用户名 -p密码 数据库名 表名> filepath/filename.sql`


- 导出一个数据库结构
    `mysqldump -h主机地址 -u用户名 -p密码 -d –add-drop-table 数据库名 > filepath/filename.sql`


- 带语言参数导出
    `mysqldump -h主机地址 -u用户名 -p密码 –default-character-set=latin1 –set-charset=gbk –skip-opt 数据库名 > filepath/filename.sql`