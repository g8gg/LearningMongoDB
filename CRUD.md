# CRUD学习
> 按一般顺序，先打开数据库(show dbs, use db)，再找到需要使用的collection(show collections)，使用db对象访问collection中的文档
> 然后进行对文档的CRUD操作

```bash
> show dbs
xxx           217.848GB
AP     I         0.078GB
local            0.078GB
test_database    0.078GB
> use xxx
switched to db xxx
> show collections
xxx
xxx_history
item
message
module
sys_log
system.indexes
user
> db.xxx.find({"belongItem": "xxx","url":/\/\//i},{url:1}).pretty()
{
	"_id" : ObjectId("55acbdb7c00d410fb82fe7ad"),
	"url" : "//message/sendExtraMessage.do"
}
{ "_id" : ObjectId("55b058e4c00d410fb82fe7bb"), "url" : "//user/block.do" }
{
	"_id" : ObjectId("55e3c394c00d7219ac8e5734"),
	"url" : "//message/sendExtraMessage.do"
}
{ "_id" : ObjectId("55fa7b3e070c3006ec53cdd8"), "url" : "//user/ban.do" }
{ "_id" : ObjectId("563c1ead070cd797c5c0f420"), "url" : "//sys/config.do" }
> db.xxx.update({_id:ObjectId("55acbdb7c00d410fb82fe7ad")},{$set:{url:"/message/sendExtraMessage.do"}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.xxx.update({_id:ObjectId("55b058e4c00d410fb82fe7bb")},{$set:{url:"/user/block.do"}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.xxx.update({_id:ObjectId("55e3c394c00d7219ac8e5734")},{$set:{url:"/message/sendExtraMessage.do"}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.xxx.update({_id:ObjectId("55fa7b3e070c3006ec53cdd8")},{$set:{url:"/user/block.do"}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.xxx.update({_id:ObjectId("563c1ead070cd797c5c0f420")},{$set:{url:"/sys/config.do"}})
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.xxx.find({"belongItem": "xxx","url":/\/\//i},{url:1}).pretty()
```

