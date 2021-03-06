#登录
>接口描述


| 接口名称 | *登录* |
| -- | -- |
| **接口地址** | */users/login* |
| **请求方式** | <mark>POST</mark> |
| **数据格式** | <code>JSON</code> |


##请求参数
[<公共传入参数>](../README.md)  

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|username|用户名|<code>string</code>|是|暂无|无|
|password|密码|<code>string</code>|是|暂无|无|


##返回参数
[<公共返回参数>](../README.md)

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|data|返回数据|<code>object</code>|是|暂无|无|

参数项：data

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|access_token|访问令牌|<code>string</code>|是|暂无|无|
|id|用户ID|<code>string</code>|是|暂无|无|
|username|用户名|<code>string</code>|是|暂无|无|
|isboss|是否老板|<code>boolean</code>|是|暂无|无|
|headportrait|头像链接|<code>string</code>|否|暂无|无|
|realname|姓名|<code>string</code>|是|暂无|无|
|sex|性别|<code>digit</code>|否|0男,1女|无|
|dept|部门|<code>object</code>|是|暂无|无|
|profession|职位|<code>string</code>|是|暂无|无|
|superior|上级领导|<code>object</code>|是|暂无|无|
|mobile1|手机号码1|<code>string</code>|否|暂无|无|
|mobile2|手机号码2|<code>string</code>|否|暂无|无|
|mobile3|手机号码3|<code>string</code>|否|暂无|无|
|qq|QQ|<code>string</code>|否|暂无|无|
|weixin|微信|<code>string</code>|否|暂无|无|
|mail|邮箱|<code>string</code>|否|暂无|无|
|curmcoin|当前M币|<code>digit</code>|是|暂无|无|
|curstarval|当前星值|<code>digit</code>|是|暂无|无|
|totalmcoin|累计M币|<code>digit</code>|是|暂无|无|
|totalstarval|累计星值|<code>digit</code>|是|暂无|无|
|remark|备注|<code>string</code>|否|暂无|无|
|createtime|创建时间|<code>string</code>|是|yyyy-MM-dd HH:mm:ss|无|
|modifytime|最近修改时间|<code>string</code>|否|yyyy-MM-dd HH:mm:ss|无|

参数项：dept

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|ID|<code>string</code>|是|暂无|无|
|name|名称|<code>string</code>|是|暂无|无|
|user|负责人|<code>object</code>|是|暂无|无|
|remark|备注|<code>string</code>|是|暂无|无|
|createtime|创建时间|<code>string</code>|是|yyyy-MM-dd HH:mm:ss|无|
|modifytime|最近修改时间|<code>string</code>|否|yyyy-MM-dd HH:mm:ss|无|


参数项：superior、dept.user

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|ID|<code>string</code>|是|暂无|无|
|header|头像链接|<code>string</code>|是|暂无|无|
|realname|姓名|<code>string</code>|是|暂无|无|

##接口示例

```
POST /oa/users/login HTTP/1.1
Host: 112.74.131.85
Cache-Control: no-cache
Content-Type: application/x-www-form-urlencoded

tt=1&vn=1.0&username=test1&password=123456
———————————————————————————————————————————————————————————
{
    "statuscode": "0000",
    "statusmsg": "ok",
    "data": {
        "profession": "部门职员",
        "qq": "11223344",
        "createtime": "2015-09-29 11:39:54",
        "mail": "13456789012@qq.com",
        "modifytime": "2015-09-29 13:44:51",
        "sex": 0,
        "mobile1": "13456789012",
        "totalmcoin": 200,
        "remark": "刚入职",
        "dept": {
            "createtime": "2015-09-29 13:39:42",
            "modifytime": "",
            "name": "市场部",
            "remark": "",
            "id": "8da0fc5f-6542-4166-bf3f-f28310487bd6",
            "user": {
                "header": "http://img5.duitang.com/uploads/item/201508/12/20150812204032_eiAQk.thumb.224_0.jpeg",
                "id": "51c58245-1921-44a2-8aed-60fc3b85cc3c",
                "realname": "赵丽"
            }
        },
        "totalstarval": 181,
        "realname": "张三",
        "access_token": "YTE5MGY1NmEtYmNiNy00NmVkLTg1MjItNzVmNTk0MzRmNTM5",
        "curstarval": 11,
        "superior": {
            "header": "http://img5.duitang.com/uploads/item/201508/12/20150812204032_eiAQk.thumb.224_0.jpeg",
            "id": "51c58245-1921-44a2-8aed-60fc3b85cc3c",
            "realname": "赵丽"
        },
        "weixin": "13456789012",
        "mobile3": "13678901234",
        "headportrait": "http://img5.duitang.com/uploads/item/201504/21/20150421H4340_uv24P.thumb.224_0.jpeg",
        "mobile2": "13567890123",
        "isboss": false,
        "curmcoin": 112,
        "id": "5d772756-3b06-4b75-9de1-f9c07310ec06",
        "username": "test1"
    },
    "usermsg": "正常"
}

```


#发送邮件
>忘记密码发送验证邮件


| 接口名称 | *发送邮件* |
| -- | -- |
| **接口地址** | */mail* |
| **请求方式** | <mark>POST</mark> |
| **数据格式** | <code>JSON</code> |


##请求参数
[<公共传入参数>](../README.md)  

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|mail|邮箱地址|<code>string</code>|是|暂无|无|


##返回参数
[<公共返回参数>](../README.md)

##接口示例

```
POST /mail?mail=1437128656@qq.com HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Cache-Control: no-cache
Postman-Token: 6ed8e017-b260-22e6-13e7-c0dc0c01a37d

———————————————————————————————————————————————————————————
{
	"statuscode":"0000",
	"statusmsg":"ok",
	"usermsg":"正常"
}

```


#修改密码
>修改密码


| 接口名称 | *修改密码* |
| -- | -- |
| **接口地址** | */passmod* |
| **请求方式** | <mark>POST</mark> |
| **数据格式** | <code>JSON</code> |


##请求参数
[<公共传入参数>](../README.md)  

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|opass|旧密码|<code>string</code>|是|暂无|无|
|npass|新密码|<code>string</code>|是|暂无|无|


##返回参数
[<公共返回参数>](../README.md)

##接口示例

```
POST /passmod?opass=1437128656&npass=1437128656 HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Cache-Control: no-cache
Postman-Token: 6ed8e017-b260-22e6-13e7-c0dc0c01a37d

———————————————————————————————————————————————————————————
{
	"statuscode":"0000",
	"statusmsg":"ok",
	"usermsg":"正常"
}

```

#获取用户资料
>接口描述


| 接口名称 | *获取用户资料* |
| -- | -- |
| **接口地址** | */users/{id}* |
| **请求方式** | <mark>GET</mark> |
| **数据格式** | <code>JSON</code> |


##请求参数
[<公共传入参数>](../README.md)  


##返回参数
[<公共返回参数>](../README.md)

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|data|返回数据|<code>object</code>|是|暂无|无|

参数项：data

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|用户ID|<code>string</code>|是|暂无|无|
|username|用户名|<code>string</code>|是|暂无|无|
|isboss|是否老板|<code>boolean</code>|是|暂无|无|
|headportrait|头像链接|<code>string</code>|否|暂无|无|
|realname|姓名|<code>string</code>|是|暂无|无|
|sex|性别|<code>digit</code>|否|0男,1女|无|
|dept|部门|<code>object</code>|是|暂无|无|
|profession|职位|<code>string</code>|是|暂无|无|
|superior|上级领导|<code>object</code>|是|暂无|无|
|mobile1|手机号码1|<code>string</code>|否|暂无|无|
|mobile2|手机号码2|<code>string</code>|否|暂无|无|
|mobile3|手机号码3|<code>string</code>|否|暂无|无|
|qq|QQ|<code>string</code>|否|暂无|无|
|weixin|微信|<code>string</code>|否|暂无|无|
|mail|邮箱|<code>string</code>|否|暂无|无|
|curmcoin|当前M币|<code>digit</code>|是|暂无|无|
|curstarval|当前星值|<code>digit</code>|是|暂无|无|
|totalmcoin|累计M币|<code>digit</code>|是|暂无|无|
|totalstarval|累计星值|<code>digit</code>|是|暂无|无|
|remark|备注|<code>string</code>|否|暂无|无|
|createtime|创建时间|<code>string</code>|是|yyyy-MM-dd HH:mm:ss|无|
|modifytime|最近修改时间|<code>string</code>|否|yyyy-MM-dd HH:mm:ss|无|

参数项：dept

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|ID|<code>string</code>|是|暂无|无|
|name|名称|<code>string</code>|是|暂无|无|
|user|负责人|<code>object</code>|是|暂无|无|
|remark|备注|<code>string</code>|是|暂无|无|
|createtime|创建时间|<code>string</code>|是|yyyy-MM-dd HH:mm:ss|无|
|modifytime|最近修改时间|<code>string</code>|否|yyyy-MM-dd HH:mm:ss|无|


参数项：superior、dept.user

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|ID|<code>string</code>|是|暂无|无|
|header|头像链接|<code>string</code>|是|暂无|无|
|realname|姓名|<code>string</code>|是|暂无|无|

##接口示例

```

———————————————————————————————————————————————————————————

```




#通讯录
>暂无

通讯录是通过两个接口实现的：  
1.查询所有用户时调用【用户管理】模块的 [ 用户列表 ] 接口   
2.查询部门下成员时，调用【部门管理】模块的  [ 部门检索 ]  接口  
通讯录部分 不再另开新接口





#文档列表
>暂无


| 接口名称 | *文档列表* |
| -- | -- |
| **接口地址** | */docs* |
| **请求方式** | <mark>GET</mark> |
| **数据格式** | <code>JSON</code> |


##请求参数
[<公共传入参数>](../README.md)  
[<公共翻页参数>](../README.md)  

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|flag|查询标识|<code>digit</code>|是|0我发出的，1我收到的|0|

##返回参数
[<公共返回参数>](../README.md)

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|data|文档数组|<code>array</code>|是|暂无|无|

参数项：data

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|文档ID|<code>string</code>|是|暂无|无|
|name|文档名称|<code>string</code>|是|暂无|无|
|size|文档大小|<code>string</code>|是|暂无|无|
|type|文档类型|<code>string</code>|是|暂无|无|
|url|文档链接|<code>string</code>|是|暂无|无|
|createtime|创建时间|<code>string</code>|是|yyyy-MM-dd HH:mm:ss|无|

##接口示例

```
GET /oa/docs?tt=1&vn=1.0&access_token=OTIzYmM3MDEtZjE3Mi00MDhhLWJiM2QtNGFkMjIyMGI3OWJh&flag=1 HTTP/1.1
Host: 112.74.131.85
Content-Type: application/json
Cache-Control: no-cache
Postman-Token: 928f557a-3ebe-0128-8073-a3bb9fb0eaab

———————————————————————————————————————————————————————————
{
	"statuscode":"0000",
	"statusmsg":"ok",
	"data":[
		{
			"createtime":"2015-12-27 16:10:53",
			"size":"29696",
			"name":"1451201320841.doc",
			"id":"11aa20f8-13bd-48ca-b681-880e10fd1fcc",
			"type":"doc",
			"url":"http://112.74.131.85:80/oa/upload/files/1451201320841.doc"
		}
	]
}

```




#文档详情
>暂无


| 接口名称 | *文档详情* |
| -- | -- |
| **接口地址** | */docs/{id}* |
| **请求方式** | <mark>GET</mark> |
| **数据格式** | <code>JSON</code> |


##请求参数
[<公共传入参数>](../README.md)  

##返回参数
[<公共返回参数>](../README.md)

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|data|文档信息|<code>object</code>|是|暂无|无|

参数项：data

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|文档ID|<code>string</code>|是|暂无|无|
|name|文档名称|<code>string</code>|是|暂无|无|
|size|文档大小|<code>string</code>|是|暂无|无|
|type|文档类型|<code>string</code>|是|暂无|无|
|url|文档链接|<code>string</code>|是|暂无|无|
|createtime|创建时间|<code>string</code>|是|yyyy-MM-dd HH:mm:ss|无|

##接口示例

```
GET /oa/docs?tt=1&vn=1.0&access_token=OTIzYmM3MDEtZjE3Mi00MDhhLWJiM2QtNGFkMjIyMGI3OWJh&flag=1 HTTP/1.1
Host: 112.74.131.85
Content-Type: application/json
Cache-Control: no-cache
Postman-Token: 928f557a-3ebe-0128-8073-a3bb9fb0eaab

———————————————————————————————————————————————————————————
{
	"statuscode":"0000",
	"statusmsg":"ok",
	"data":{
			"createtime":"2015-12-27 16:10:53",
			"size":"29696",
			"name":"1451201320841.doc",
			"id":"11aa20f8-13bd-48ca-b681-880e10fd1fcc",
			"type":"doc",
			"url":"http://112.74.131.85:80/oa/upload/files/1451201320841.doc"
		}
}

```




#删除文档
>暂无


| 接口名称 | *删除文档* |
| -- | -- |
| **接口地址** | */docs/{id}* |
| **请求方式** | <mark>DELETE</mark> |
| **数据格式** | <code>JSON</code> |


##请求参数
[<公共传入参数>](../README.md)  


##返回参数
[<公共返回参数>](../README.md)

##接口示例

```

———————————————————————————————————————————————————————————

```




#转发文档
>暂无


| 接口名称 | *删除文档* |
| -- | -- |
| **接口地址** | */docs* |
| **请求方式** | <mark>POST</mark> |
| **数据格式** | <code>JSON</code> |


##请求参数
[<公共传入参数>](../README.md)  

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|ids|文档ID|<code>string</code>|是|暂无|无|
|uid|用户ID|<code>string</code>|是|多个用英文逗号分隔|无|


##返回参数
[<公共返回参数>](../README.md)

##接口示例

```

———————————————————————————————————————————————————————————

```


#效率统计
>如果按用户查询会返回选择用户的工作效率，如果是按部门查询，会返回部门下所有人的工作效率


| 接口名称 | *效率查询* |
| -- | -- |
| **接口地址** | */efficquery* |
| **请求方式** | <mark>GET</mark> |
| **数据格式** | <code>JSON</code> |


##请求参数
[<公共传入参数>](../README.md)  

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|flag|查询标识|<code>digit</code>|否|0按部门查询，1按用户查询，2按公司查询|1
|id|ID信息|<code>string</code>|否|如果是按部门查询，那么这里是传部门ID；如果是用户查询，这里是传用户ID，如果是公司查询为空|自己|
|started|查询开始年月|<code>string</code>|否|yyyy-MM-dd|本月1号|
|ended|查询结束年月|<code>string</code>|否|yyyy-MM-dd|今天|


##返回参数
[<公共返回参数>](../README.md)

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|data|效率数据|<code>object</code>|是|暂无|无|

参数项：data

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|equip|设备效率|<code>string</code>|是|百分比，如30%|无|
|dept|部门效率|<code>object</code>|否|当flag为0时，百分比，如30%|无|
|users|用户效率|<code>object</code>|否|当flag为1时，百分比，如30%|无|
|company|公司效率|<code>string</code>|否|当flag为2时，百分比，如30%|无|

参数项：dept

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|ID|<code>string</code>|是|暂无|无|
|name|部门名称|<code>string</code>|是|暂无|无|
|effic|效率|<code>string</code>|是|百分比，如30%|无|

参数项：users

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|ID|<code>string</code>|是|暂无|无|
|effic|效率|<code>string</code>|是|百分比，如30%|无|
|header|头像链接|<code>string</code>|是|暂无|无|
|realname|姓名|<code>string</code>|是|暂无|无|

##接口示例

```

———————————————————————————————————————————————————————————

```





#图片上传
>暂无


| 接口名称 | *图片上传* |
| -- | -- |
| **接口地址** | */image/upload* |
| **请求方式** | <mark>POST</mark> |
| **数据格式** | <code>JSON</code> |


##请求参数
[图片上传流]


##返回参数
[<公共返回参数>](../README.md)

##接口示例

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|url|地址|<code>string</code>|是|暂无|无|

```
暂无

```

#文件上传
>暂无


| 接口名称 | *文件上传* |
| -- | -- |
| **接口地址** | */file/upload* |
| **请求方式** | <mark>POST</mark> |
| **数据格式** | <code>JSON</code> |


##请求参数
[<公共传入参数>](../README.md)    
[图片上传流]  


##返回参数
[<公共返回参数>](../README.md)

##接口示例

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|文件ID|<code>string</code>|是|暂无|无|
|url|地址|<code>string</code>|是|暂无|无|

```
暂无

```




#版本检测
>暂无


| 接口名称 | *版本检测* |
| -- | -- |
| **接口地址** | */version* |
| **请求方式** | <mark>GET</mark> |
| **数据格式** | <code>JSON</code> |


##请求参数
[<公共传入参数>](../README.md)    


##返回参数
[<公共返回参数>](../README.md)

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|data|数据|<code>object</code>|是|暂无|无|

参数项：data

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|updated|是否需要更新|<code>boolean</code>|是|暂无|无|
|vers|版本数据|<code>object</code>|否|当updated为true时才有值|无|

参数项：vers

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|code|版本编码|<code>digit</code>|是|暂无|无|
|name|版本名称|<code>string</code>|是|暂无|无|
|link|版本链接|<code>string</code>|是|暂无|无|
|type|终端类型|<code>digit</code>|是|1安卓，2iOS|无|
|content|版本描述|<code>string</code>|是|暂无|无|
|createtime|创建时间|<code>string</code>|是|yyyy-MM-dd HH:mm:ss|无|
|isforce|是否强制升级|<code>boolean</code>|是|暂无|无|

##接口示例
```
暂无

```

