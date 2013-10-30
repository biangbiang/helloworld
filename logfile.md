#日志下载接口文档
---

## 获取日志文件列表

#### http 请求地址

https://www.upyun.com/http-logs-list.api.php

#### http请求方法

POST

####请求参数

| 参数名        | 是否必须 | 说明
----------------| ------ | -------------------
| bucket_name   | 是 | 空间名 
| domain        | 是 | 域名，如 biangbiang.b0.upaiyun.com
| date          | 是 | 日期，格式为yyyy-mm-dd，如 2013-10-25
| account_name  | 是 | upyun帐号名
| username      | 是 | 操作员帐号
| password      | 是 | 操作员密码


####返回参数（返回值经过json编码，要使用返回值请解码）

| 参数名        | 说明
|---------------|-------------------
| no            | 0表示返回正确结果，1表示返回错误
| msg           | 当返回错误时，msg记录了错误信息
| data          | 当返回正确结果时，data记录了返回结果：file是日志文件下载地址获取接口里面的file（需解码），size是该文件大小

####返回结果

```json
{
	    "no":0,
    	"msg":" ",
    	"data":[
	    	{
		    	"file":"\/2013-10-24\/y.\/biangbiang.b0.upaiyun.com.2013-10-24-00.cbf01e0dc5266cff8ac3121668011b0d.gz",
			    "size":"0.02 KB"
    		},
	    	{……},
	    	……
    	]
}
```


---

## 获取日志文件下载地址

#### http 请求地址

https://www.upyun.com/http-logs-load.api.php


####http请求方法

POST

####需要参数：

| 参数名        | 是否必须 | 说明
----------------| ------ | -------------------
| bucket_name   |  是 | 空间名 
| domain        |  是 | 域名，如 biangbiang.b0.upaiyun.com
| file          |  是 | 文件名，日志文件列表获取接口里得到的file参数，如：/2013-10-24/y./biangbiang.b0.upaiyun.com.2013-10-24-00.cbf01e0dc5266cff8ac3121668011b0d.gz
| account_name  |  是 | upyun帐号名
| username      |  是 | 操作员帐号
| password      |  是 | 操作员密码

####返回参数（返回值经过json编码，要使用返回值请解码）

| 参数名        | 说明
|---------------|-------------------
| no            | 0表示返回正确结果，1表示返回错误
| msg           | 当返回错误时，msg记录了错误信息
| data          | 当返回正确结果时，data记录了下载地址

####返回结果

```json
{
    	"no":0,
    	"msg":" ",
    	"data":"http:\/\/jeijeog:3Kb5ExWPle@122.225.106.147:830\/2013-10-24\/y.\/biangbiang.b0.upaiyun.com.2013-10-24-00.cbf01e0dc5266cff8ac3121668011b0d.gz"
}
```

