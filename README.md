# Epay
2020.02彩虹易支付原版开源

# 部署

## 宝塔部署

1. 创建站点

   填写你的域名，然后把域名指向当前服务器

   ![image-20230526110225275](https://david-1255528809.cos.ap-beijing.myqcloud.com/uPic/2023-05-26/image-20230526110225275.png)

2. 上传文件

   把当前所有源码上传到对应的路径上

![image-20230526110811872](https://david-1255528809.cos.ap-beijing.myqcloud.com/uPic/2023-05-26/image-20230526110811872.png)

3. 设置伪静态

![image-20230526111102249](https://david-1255528809.cos.ap-beijing.myqcloud.com/uPic/2023-05-26/image-20230526111102249.png)

```
location / {
 if (!-e $request_filename) {
   rewrite ^/(.[a-zA-Z0-9\-\_]+).html$ /index.php?mod=$1 last;
 }
 rewrite ^/pay/(.*)$ /pay.php?s=$1 last;
}
location ^~ /plugins {
  deny all;
}
location ^~ /includes {
  deny all;
}
```

