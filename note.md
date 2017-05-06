# 2017-04-15

1. 
*Bug*: 将数据库布置到阿里云服务器，结果动态调用楼层中的总共楼层数目时，出现“??”乱码，使用的是"select distinct ..."语句。
*Reason*:因为数据库中 character_set_server,default_client_connection为设置为utf8，可以通过“show variables like "character%" 进行查看”单单设置所建database为的charset为utf是不够的，(参考)[http://cenalulu.github.io/mysql/mysql-mojibake/]
*Correction*:通过在mysql.init 中添加character_set_server=utf8