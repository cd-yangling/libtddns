# tddns
腾讯 DDNS Shell Scripts

## 介绍

腾讯云的域名解析服务官方不提供基于 shell 版本。为了方便一些嵌入式设备或者软路由使用，我就自己编写了一个 shell 版本的 SDK

已知问题: 参数名称不能携带 `.` 字符。 这是 shell 不被允许的。目前有一个解决方案，但是我还没有实施它。至少 DDNS 接口中不会存在这样的情况。如果您有兴趣你可以参考 [这里](https://stackoverflow.com/questions/9761973/using-variable-as-a-key-in-an-bash-associative-array) 来修复参数名称携带 `.` 的问题。

注意事项: 该脚本仅仅实现了 [获取解析记录列表](https://cloud.tencent.com/document/product/302/8517) 和 [修改解析记录](https://cloud.tencent.com/document/product/302/8511)

参考文档: [腾讯云解析文档](https://cloud.tencent.com/document/product/302)

## 使用方法

### 获取解析记录列表

```sh
source "$(dirname $0)/libfntddns"
export SecretKey=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
export SecretId=yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy
curl -fsS $(RecordList qcloud.com)
```

### 修改解析记录

```sh
source "$(dirname $0)/libfntddns"
export SecretKey=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
export SecretId=yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy
curl -fsS $(RecordModify qcloud.com id www A 默认 192.168.0.2)
```
