## 进入mongo
use admin
`创建超级管理员`
db.createUser(
  {
    user: "欲创建的超级管理账号",
    pwd: "欲创建的超级管理账号的密码",
    roles: [ { role: "userAdminAnyDatabase", db: "admin" } ]
  }
)  

`验证是否成功 ， 成功返回 1`  

db.auth("bixinseoAdmin","s2CKFngFPq4NuA6D")  

`退出修改配置文件`  

disabled
security:
authorization: enabled  

`重启mongodb`
use admin
db.auth("欲创建的超级管理账号","欲创建的超级管理账号的密码")
use bixinseo
db.createUser(
{
    user: "欲创建的数据库用户",
    pwd: "欲创建的数据库用户的密码",
    roles: [{ role: "dbOwner", db:"这列填写数据库" }]
})
