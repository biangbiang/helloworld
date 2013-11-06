#数据导入临时API接口文档
---

##上传文件

####上传说明

* 图片类空间无法上传非图片类文件

####请求方法

    > PUT /demobucket/a.txt HTTP/1.1
    > Host: demo.upyun.com
    > Content-Length: 26

    ...文件内容...    

#### 请求参数

| 请求参数      | 是否必须 | 说明
--------------- | -------- | -----------
| Host          | 是       | 又拍云 API 的接入地址
| Content-Length| 是       | 请求内容长度，但不包括Headers部分。若发起的是 PUT、POST 等上传请求时，则必须设置该参数。详细规范请参阅 [RFC 2616][1]


####返回内容

#####成功时：

    > HTTP/1.1 200 OK
    
#####失败时：

    > HTTP/1.1 400 Bad Request
    400 Bad Request   //body内容


  [1]: http://tools.ietf.org/html/rfc2616#section-14.13
