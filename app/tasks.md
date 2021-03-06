#任务列表
>按时间逆序排列

| 接口名称 | *任务列表* |
| -- | -- |
| **接口地址** | */tasks* |
| **请求方式** | <mark>GET</mark> |
| **数据格式** | <code>JSON</code> |


##请求参数
[<公共传入参数>](../README.md)  
[<公共翻页参数>](../README.md)

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|flag|查询标识|<code>digit</code>|是|0全部，1上级任务，2协同工作，3下属工作，4未汇报，5提醒，6任务汇报，7工作审批，8日常任务|0|

##返回参数
[<公共返回参数>](../README.md)

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|data|任务数组|<code>array</code>|是|暂无|无|
|totalpgs|总页数|<code>digit</code>|是|暂无|无|
|totalels|记录总数|<code>digit</code>|是|暂无|无|

参数项：data

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|任务ID|<code>string</code>|是|暂无|无|
|creator|创建人|<code>object</code>|是|暂无|无|
|startdate|计划开始日期|<code>string</code>|是|暂无|无|
|enddate|计划结束日期|<code>string</code>|是|暂无|无|
|createtime|创建时间|<code>string</code>|是|暂无|无|
|status|任务状态|<code>digit</code>|是|0进行中，1已汇报，2已完成|无|
|isdailytask|是否日常任务|<code>boolean</code>|是|暂无|无|
|title|任务标题|<code>string</code>|是|暂无|无|
|content|任务内容|<code>string</code>|是|暂无|无|
|operators|执行人|<code>array</code>|是|暂无|无|

参数项：user

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|ID|<code>string</code>|是|暂无|无|
|header|头像链接|<code>string</code>|是|暂无|无|
|realname|姓名|<code>string</code>|是|暂无|无|

参数项：operators

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|ID|<code>string</code>|是|暂无|无|
|header|头像链接|<code>string</code>|是|暂无|无|
|realname|姓名|<code>string</code>|是|暂无|无|
|isremind|是否提醒|<code>boolean</code>|是|暂无|无|
|remindtime|提醒时间|<code>string</code>|是|yyyy-MM-dd HH:mm|无|

##接口示例

```
GET /oa/tasks?tt=1&vn=1.0&access_token=MTgxOWI5MzMtYTcwMy00ZDQ1LWEwN2YtN2Y1ZGIxYWFhYjJm HTTP/1.1
Host: localhost:7778
Cache-Control: no-cache
———————————————————————————————————————————————————————————
{
	"statuscode":"0000",
	"statusmsg":"ok",
	"data":[
		{
			"creator":{
				"header":"http://cdn.duitang.com/uploads/item/201504/21/20150421H4327_3eRXN.thumb.224_0.jpeg",
				"id":"d9a5648a-65dd-46ef-add8-4837795ce8b4",
				"realname":"李四"
			},
			"createtime":"2015-09-29 17:51:32",
			"enddate":"2015-10-01 00:00:00",
			"operators":[
				{
					"header":"http://img5.duitang.com/uploads/item/201504/21/20150421H4340_uv24P.thumb.224_0.jpeg",
					"id":"5d772756-3b06-4b75-9de1-f9c07310ec06",
					"isremind":false,
					"realname":"张三"
				},
				{
					"header":"http://img5.duitang.com/uploads/item/201503/26/20150326161657_aL8FW.jpeg",
					"id":"d47539b3-9820-4086-9582-f629d2ef0630",
					"isremind":false,
					"realname":"王五"
				}
			],
			"id":"243d6cd4-629b-4da8-98ac-ee1addbee2e6",
			"startdate":"2015-09-29 00:00:00",
			"title":"任务1",
			"content":"任务1内容描述",
			"status":0
		},
		{
			"creator":{
				"header":"http://img5.duitang.com/uploads/item/201508/12/20150812204032_eiAQk.thumb.224_0.jpeg",
				"id":"51c58245-1921-44a2-8aed-60fc3b85cc3c",
				"realname":"赵丽"
			},
			"createtime":"2015-09-29 17:51:32",
			"enddate":"2015-10-01 00:00:00",
			"operators":[
				{
					"header":"http://img5.duitang.com/uploads/item/201503/26/20150326161657_aL8FW.jpeg",
					"id":"d47539b3-9820-4086-9582-f629d2ef0630",
					"isremind":false,
					"realname":"王五"
				},
				{
					"header":"http://img5.duitang.com/uploads/item/201504/21/20150421H4340_uv24P.thumb.224_0.jpeg",
					"id":"5d772756-3b06-4b75-9de1-f9c07310ec06",
					"isremind":false,
					"realname":"张三"
				}
			],
			"id":"d78ab909-7994-4fc0-8dc9-9200e749782c",
			"startdate":"2015-09-29 00:00:00",
			"title":"任务2",
			"content":"任务2内容描述",
			"status":0
		}
	],
	"usermsg":"正常"
}
```






***

#任务详细
>接口描述


| 接口名称 | *任务详细* |
| -- | -- |
| **接口地址** | */tasks/{id}* |
| **请求方式** | <mark>GET</mark> |
| **数据格式** | <code>JSON</code> |


##请求参数
[<公共传入参数>](../README.md)

##返回参数
[<公共返回参数>](../README.md)


|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|data|数据详细|<code>object</code>|是|暂无|无|

参数项：data

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|ID|<code>string</code>|是|暂无|无|
|title|任务标题|<code>string</code>|是|暂无|无|
|content|任务内容|<code>string</code>|是|暂无|无|
|status|任务状态|<code>string</code>|是|0进行中，1已汇报，2已完成|无|
|startdate|计划开始日期|<code>string</code>|是|yyyy-MM-dd|无|
|enddate|计划结束日期|<code>string</code>|是|yyyy-MM-dd|无|
|reportdate|汇报时间|<code>string</code>|否|yyyy-MM-dd HH:mm:ss|无|
|finishdate|完成时间|<code>string</code>|否|yyyy-MM-dd HH:mm:ss|无|
|mcoin|任务M币|<code>digit</code>|是|暂无|无|
|starval|任务星值|<code>digit</code>|是|暂无|无|
|isdailytask|是否日常任务|<code>boolean</code>|是|暂无|无|
|creator|创建人|<code>object</code>|是|暂无|无|
|report|最近汇报记录|<code>object</code>|否|暂无|无|
|remark|备注|<code>string</code>|否|暂无|无|
|createtime|创建时间|<code>string</code>|是|yyyy-MM-dd HH:mm:ss|无|
|modifytime|最近修改时间|<code>string</code>|否|yyyy-MM-dd HH:mm:ss|无|
|operators|执行人|<code>array</code>|是|暂无|无|
|attachs|任务附件|<code>array</code>|否|暂无|无|
|images|任务图片|<code>array</code>|否|暂无|无|

参数项：creator

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|ID|<code>string</code>|是|暂无|无|
|header|头像链接|<code>string</code>|是|暂无|无|
|realname|姓名|<code>string</code>|是|暂无|无|

参数项：report

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|content|汇报内容|<code>string</code>|是|暂无|无|
|images|汇报图片|<code>string</code>|否|图片链接，多个用英文逗号分隔|无|
|attachs|汇报附件|<code>array</code>|否|暂无|无|
|createtime|创建时间|<code>string</code>|是|yyyy-MM-dd HH:mm:ss|无|

参数项：operators

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|ID|<code>string</code>|是|暂无|无|
|header|头像链接|<code>string</code>|是|暂无|无|
|realname|姓名|<code>string</code>|是|暂无|无|
|isremind|是否提醒|<code>boolean</code>|是|暂无|无|
|remindtime|提醒时间|<code>string</code>|是|yyyy-MM-dd HH:mm|无|
|mcoin|分配M币|<code>digit</code>|是|任务审批通过后才有值|无|
|starval|分配星值|<code>digit</code>|是|任务审批通过后才有值|无|

参数项：attachs、report.attachs

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|id|文档ID|<code>string</code>|是|暂无|无|
|name|文档名称|<code>string</code>|是|暂无|无|
|size|文档大小|<code>string</code>|是|暂无|无|
|type|文档类型|<code>string</code>|是|暂无|无|
|url|文档链接|<code>string</code>|是|暂无|无|
|createtime|创建时间|<code>string</code>|是|yyyy-MM-dd HH:mm:ss|无|

参数项：images

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|image|图片链接|<code>string</code>|是|暂无|无|


##接口示例

```
GET /oa/tasks/d78ab909-7994-4fc0-8dc9-9200e749782c?tt=1&vn=1.0&access_token=OWMxNzIxMGQtN2ZiMC00N2RjLWEzNjgtZjU1YjFkMWUxMTRh HTTP/1.1
Host: localhost:7778
Cache-Control: no-cache
———————————————————————————————————————————————————————————
{
	"statuscode":"0000",
	"statusmsg":"ok",
	"data":{
		"creator":{
			"header":"http://img5.duitang.com/uploads/item/201508/12/20150812204032_eiAQk.thumb.224_0.jpeg",
			"id":"51c58245-1921-44a2-8aed-60fc3b85cc3c",
			"realname":"赵丽"
		},
		"createtime":"2015-09-29 17:51:32",
		"starval":3,
		"isdailytask":false,
		"modifytime":"",
		"reportdate":"",
		"finishdate":"",
		"remark":"",
		"title":"任务2",
		"startdate":"2015-09-29 00:00:00",
		"content":"任务2内容描述",
		"mcoin":4,
		"attachs":[],
		"enddate":"2015-10-01 00:00:00",
		"operators":[
			{
				"header":"http://img5.duitang.com/uploads/item/201503/26/20150326161657_aL8FW.jpeg",
				"id":"d47539b3-9820-4086-9582-f629d2ef0630",
				"isremind":false,
				"realname":"王五"
			},
			{
				"header":"http://img5.duitang.com/uploads/item/201504/21/20150421H4340_uv24P.thumb.224_0.jpeg",
				"id":"5d772756-3b06-4b75-9de1-f9c07310ec06",
				"isremind":false,
				"realname":"张三"
			}
		],
		"id":"d78ab909-7994-4fc0-8dc9-9200e749782c",
		"status":0
	},
	"usermsg":"正常"
}
```

***




#新增任务
>自己不能是任务的执行人


| 接口名称 | *新增任务* |
| -- | -- |
| **接口地址** | */tasks* |
| **请求方式** | <mark>POST</mark> |
| **数据格式** | <code>JSON</code> |

##请求参数
[<公共传入参数>](../README.md)

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|title|任务标题|<code>string</code>|是|任务标题在系统内唯一不能重复|无|
|content|任务内容|<code>string</code>|是|暂无|无|
|isdailytask|是否日常任务|<code>boolean</code>|否|暂无|false|
|startdate|计划开始日期|<code>string</code>|是|暂无|无|
|enddate|计划结束日期|<code>string</code>|是|暂无|无|
|mcoin|任务M币|<code>digit</code>|否|暂无|0|
|starval|任务星值|<code>digit</code>|否|暂无|0|
|operators|执行人|<code>string</code>|是|用户ID，多个用英文逗号分隔|无|
|attachs|任务附件|<code>string</code>|否|文件链接，多个用英文逗号分隔|无|
|images|任务图片|<code>string</code>|否|图片链接，多个用英文逗号分隔|无|

##返回参数
[<公共返回参数>](../README.md)


##接口示例

```
POST /oa/tasks?tt=1&vn=1.0&access_token=OWMxNzIxMGQtN2ZiMC00N2RjLWEzNjgtZjU1YjFkMWUxMTRh HTTP/1.1
Host: localhost:7778
Cache-Control: no-cache
Content-Type: application/x-www-form-urlencoded

title=测试新增任务接口1&content=测试新增任务接口1内容&startdate=2015-10-01&enddate=2015-10-03&operators=d9a5648a-65dd-46ef-add8-4837795ce8b4%2C51c58245-1921-44a2-8aed-60fc3b85cc3c
———————————————————————————————————————————————————————————
{
    "statuscode": "0000",
    "statusmsg": "ok",
    "usermsg": "正常"
}
```

***







#删除任务
>接口描述

| 接口名称 | *删除任务* |
| -- | -- |
| **接口地址** | */tasks/{id}* |
| **请求方式** | <mark>DELETE</mark> |
| **数据格式** | <code>JSON</code> |

##请求参数
[<公共传入参数>](../README.md)

##返回参数
[<公共返回参数>](../README.md)

##接口示例

```
DELETE /oa/tasks/350d256f-d574-4634-9079-083e6ef953af?tt=1&vn=1.0&access_token=OWMxNzIxMGQtN2ZiMC00N2RjLWEzNjgtZjU1YjFkMWUxMTRh HTTP/1.1
Host: localhost:7778
Cache-Control: no-cache
———————————————————————————————————————————————————————————
{
	"statuscode":"0000",
	"statusmsg":"ok",
	"usermsg":"正常"
}
```

***



#任务提醒
>接口描述

| 接口名称 | *任务提醒* |
| -- | -- |
| **接口地址** | */tasks/{id}/reminder* |
| **请求方式** | <mark>POST</mark> |
| **数据格式** | <code>JSON</code> |

##请求参数
[<公共传入参数>](../README.md)

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|isremind|是否提醒|<code>boolean</code>|是|暂无|无|
|remindtime|提醒时间|<code>string</code>|是|yyyy-MM-dd HH:mm|无|

##返回参数
[<公共返回参数>](../README.md)

##接口示例

```
POST /oa/tasks/d78ab909-7994-4fc0-8dc9-9200e749782c/reminder?tt=1&vn=1.0&access_token=OWMxNzIxMGQtN2ZiMC00N2RjLWEzNjgtZjU1YjFkMWUxMTRh HTTP/1.1
Host: localhost:7778
Cache-Control: no-cache
———————————————————————————————————————————————————————————
{
    "statuscode": "0000",
    "statusmsg": "ok",
    "usermsg": "正常"
}
```

***






#任务汇报
>接口描述

| 接口名称 | *任务汇报* |
| -- | -- |
| **接口地址** | */tasks/{id}/reports* |
| **请求方式** | <mark>POST</mark> |
| **数据格式** | <code>JSON</code> |

##请求参数
[<公共传入参数>](../README.md)

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|content|汇报内容|<code>string</code>|是|暂无|无|
|images|汇报图片|<code>string</code>|否|图片链接，多个用英文逗号分隔|无|
|attachs|汇报附件|<code>string</code>|否|文件链接，多个用英文逗号分隔|无|

##返回参数
[<公共返回参数>](../README.md)

##接口示例

```
POST /oa/tasks/d78ab909-7994-4fc0-8dc9-9200e749782c/reports?tt=1&vn=1.0&access_token=OWMxNzIxMGQtN2ZiMC00N2RjLWEzNjgtZjU1YjFkMWUxMTRh HTTP/1.1
Host: localhost:7778
Cache-Control: no-cache
Content-Type: application/x-www-form-urlencoded

content=完美完成
———————————————————————————————————————————————————————————
{
    "statuscode": "0000",
    "statusmsg": "ok",
    "usermsg": "正常"
}
```

***






#任务审批
>接口描述

| 接口名称 | *任务审批* |
| -- | -- |
| **接口地址** | */tasks/{id}/approvals* |
| **请求方式** | <mark>POST</mark> |
| **数据格式** | <code>JSON</code> |

##请求参数
[<公共传入参数>](../README.md)

|编码|名称|类型|必输|说明|默认值|
|:---|:---|:---|:--:|:---|:-----|
|isfinish|是否通过|<code>boolean</code>|是|为true时operators不能为空；为false时任务会被重置回完成中状态|无|
|operators|执行人分值分配|<code>string</code>|否|用户ID:M币:星值，多个用英文逗号分隔|无|

##返回参数
[<公共返回参数>](../README.md)

##接口示例

```
POST /oa/tasks/d78ab909-7994-4fc0-8dc9-9200e749782c/approvals?tt=1&vn=1.0&access_token=OWMxNzIxMGQtN2ZiMC00N2RjLWEzNjgtZjU1YjFkMWUxMTRh HTTP/1.1
Host: localhost:7778
Cache-Control: no-cache
Content-Type: application/x-www-form-urlencoded

isfinish=true&operators=5d772756-3b06-4b75-9de1-f9c07310ec06:100:1,d47539b3-9820-4086-9582-f629d2ef0630:200:2
———————————————————————————————————————————————————————————
{
    "statuscode": "0000",
    "statusmsg": "ok",
    "usermsg": "正常"
}
```

***
