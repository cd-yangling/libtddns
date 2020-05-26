# tddns
腾讯 DDNS Shell Scripts

## 介绍

腾讯云的域名解析服务官方不提供基于 shell 版本。 非常适合用于一些嵌入式小设备使用或者软路由等。

注意: 该脚本仅仅实现了 [获取解析记录列表](https://cloud.tencent.com/document/product/302/8517) 和 [修改解析记录](https://cloud.tencent.com/document/product/302/8511)

参考: [腾讯云解析文档](https://cloud.tencent.com/document/product/302)

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
