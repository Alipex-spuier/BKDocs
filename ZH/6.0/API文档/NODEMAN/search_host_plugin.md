### 功能描述

查询插件列表

### 请求参数

| 字段 | 类型 | 必选 |  描述 |
|-----------|------------|--------|------------|
| bk_app_code  |  string    | 是 | 应用 ID     |
| bk_app_secret|  string    | 是 | 安全密钥(应用 TOKEN)，可以通过 蓝鲸智云开发者中心 -&gt; 点击应用 ID -&gt; 基本信息 获取 |
| bk_token     |  string    | 否 | 当前用户登录态，bk_token 与 bk_username 必须一个有效，bk_token 可以通过 Cookie 获取 |
| bk_username  |  string    | 否 | 当前用户用户名，应用免登录态验证白名单中的应用，用此字段指定当前用户 |

#### 接口参数

| 字段     | 类型       | 必选 |描述                  |
|----------|------------|----------|-----------------------------|
| bk_biz_id | list | 否 | 业务 ID |
| bk_host_id | list | 否 | 主机 ID |
| conditions | list | 否 | 搜索条件，支持 os_type, ip, status <br> version, bk_cloud_id, node_from 和 模糊搜索 query |
| exclude_hosts | list | 否 | 跨页全选排除主机 |
| page | int | 否 | 当前页数 |
| pagesize | int | 否 | 分页大小 |
| only_ip | Boolean | 否 | 只返回 IP |

### 请求参数示例
```plain
{
    "pagesize":50,
    "page":1
  	"bk_host_id": [111],
  	"only_ip": true,
    "conditions":[
        {
            "key":"inner_ip",
            "value":[
                "127.0.0.1"
            ]
        },
        {
            "key":"bk_cloud_id",
            "value":[
                0
            ]
        },
        {
            "key":"version",
            "value":[
                "1.6.15"
            ]
        },
        {
            "key":"basereport",
            "value":[
                "10.8.40"
            ]
        },
        {
            "key":"os_type",
            "value":[
                "LINUX"
            ]
        }
    ],
    "bk_biz_id":[
        5
    ]
}
```

### 返回结果示例
```plain
{
    "message": "",
    "code": 0,
    "data": {
        "total": 1,
        "list": [
            {
                "bk_biz_id": 5,
                "status": "RUNNING",
                "node_from": "NODE_MAN",
                "operate_permission": true,
                "bk_host_id": 35,
                "bk_cloud_id": 0,
                "node_type": "AGENT",
                "version": "1.6.15",
                "inner_ip": "127.0.0.1",
                "bk_cloud_name": "直连区域",
                "plugin_status": [
                    {
                        "status": "TERMINATED",
                        "host_id": 35,
                        "version": "1.10.67",
                        "name": "bkmonitorbeat"
                    },
                    {
                        "status": "TERMINATED",
                        "host_id": 35,
                        "version": "",
                        "name": "bkmonitorproxy"
                    },
                    {
                        "status": "TERMINATED",
                        "host_id": 35,
                        "version": "1.12.38",
                        "name": "processbeat"
                    },
                    {
                        "status": "TERMINATED",
                        "host_id": 35,
                        "version": "1.4.26",
                        "name": "exceptionbeat"
                    },
                    {
                        "status": "UNREGISTER",
                        "host_id": 35,
                        "version": "",
                        "name": "gsecmdline"
                    },
                    {
                        "status": "TERMINATED",
                        "host_id": 35,
                        "version": "7.1.34",
                        "name": "bkunifylogbeat"
                    },
                    {
                        "status": "RUNNING",
                        "host_id": 35,
                        "version": "10.8.40",
                        "name": "basereport"
                    }
                ],
                "os_type": "LINUX",
                "status_display": "正常",
                "bk_biz_name": "节点管理测试用",
                "job_result": {
                    "instance_id": "host|instance|host|35",
                    "status": "FAILED",
                    "job_id": 294,
                    "current_step": "正在重装"
                }
            }
        ]
    },
    "result": true,
    "request_id": "b858d09118cf4c41a2035380ebb45421"
}
```
