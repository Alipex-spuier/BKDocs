### 功能描述

查询接入点列表

### 请求参数

| 字段 | 类型 | 必选 |  描述 |
|-----------|------------|--------|------------|
| bk_app_code  |  string    | 是 | 应用 ID     |
| bk_app_secret|  string    | 是 | 安全密钥(应用 TOKEN)，可以通过 蓝鲸智云开发者中心 -&gt; 点击应用 ID -&gt; 基本信息 获取 |
| bk_token     |  string    | 否 | 当前用户登录态，bk_token 与 bk_username 必须一个有效，bk_token 可以通过 Cookie 获取 |
| bk_username  |  string    | 否 | 当前用户用户名，应用免登录态验证白名单中的应用，用此字段指定当前用户 |


### 返回结果示例
```plain
{
    "message": "",
    "code": 0,
    "data": [
        {
            "is_enabled": true,
            "region_id": "test",
            "creator": [
                "xxxx"
            ],
            "city_id": "test",
            "id": 1,
            "zk_account": "zk",
            "port_config": {
                "tracker_port": 10030,
                "bt_port": 10020,
                "api_server_port": 50002,
                "btsvr_thrift_port": 58930,
                "io_port": 48668,
                "bt_port_start": 60020,
                "db_proxy_port": 58859,
                "data_port": 58625,
                "trunk_port": 48329,
                "bt_port_end": 60030,
                "agent_thrift_port": 48669,
                "proc_port": 50000,
                "file_svr_port": 58925
            },
            "bscp_config": {
                "GATEWAY_HOSTNAME": "127.0.0.1"
            },
            "taskserver": [
                {
                    "inner_ip": "127.0.0.1",
                    "outer_ip": ""
                }
            ],
            "btfileserver": [
                {
                    "inner_ip": "127.0.0.1",
                    "outer_ip": ""
                }
            ],
            "package_inner_url": "http://127.0.0.1/download/",
            "status": "normal",
            "description": "GSE默认接入点",
            "zk_hosts": [
                {
                    "zk_port": "2181",
                    "zk_ip": "127.0.0.1"
                },
                {
                    "zk_port": "2181",
                    "zk_ip": "127.0.0.2"
                },
                {
                    "zk_port": "2181",
                    "zk_ip": "127.0.0.3"
                }
            ],
            "proxy_package": [
                "gse_client-windows-x86.tgz",
                "gse_client-windows-x86_64.tgz",
                "gse_client-linux-x86.tgz",
                "gse_client-linux-x86_64.tgz"
            ],
            "is_default": true,
            "permissions": {
                "edit": true,
                "view": true,
                "delete": true
            },
            "name": "IDC",
            "dataserver": [
                {
                    "inner_ip": "127.0.0.1",
                    "outer_ip": "127.0.0.1"
                }
            ],
            "agent_config": {
                "windows": {
                    "setup_path": "c:\\gse",
                    "hostid_path": "C:\\gse\\data\\host\\hostid",
                    "log_path": "c:\\gse\\logs",
                    "data_path": "c:\\gse\\data",
                    "temp_path": "c:\\Temp",
                    "host_id": "C:\\gse\\data\\host\\hostid",
                    "dataipc": 47000
                },
                "linux": {
                    "setup_path": "/usr/local/gse",
                    "hostid_path": "/var/lib/gse/host/hostid",
                    "log_path": "/var/log/gse",
                    "data_path": "/var/lib/gse",
                    "temp_path": "/tmp",
                    "host_id": "/var/lib/gse/host/hostid",
                    "dataipc": "/var/run/ipc.state.report.cloud",
                    "run_path": "/var/run/gse"
                }
            },
            "ap_type": "system",
            "nginx_path": "/data/bkee/public/bknodeman/download/",
            "package_outer_url": "http://127.0.0.1/download/"
        }
    ],
    "result": true,
    "request_id": "917adbb0c706483cb4fbca8231dceca9"
}
```
