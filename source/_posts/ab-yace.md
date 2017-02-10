title: ab压测
tags:
  - ab压测
categories: [PHP]
author: admin
date: 2017-02-10 16:39:00
---
**apache ab 压测命令及其相关参数**
```
ab -n 1000 -c 100 http://domain/index.php
```
参数说明 : 
 - -n 请求数
 - -c 并发数

返回参数说明:
```
Server Software:        swoole-http-server  ##服务器版本
Server Hostname:        127.0.0.1   ##请求的服务器
Server Port:            80 ##请求端口

Document Path:          /	##请求的页面
Document Length:        28 bytes  ##页面长度

Concurrency Level:      100  ##并发数
Time taken for tests:   0.928seconds  ##共使用了多少时间
Complete requests:      1000   ##请求数
Failed requests:        0   ##失败请求
Write errors:           0  
Total transferred:      191000 bytes  ##总共传输字节数，包含http的头信息等
HTML transferred:       28000 bytes  ##html字节数，实际的页面传递字节数
Requests per second:    1078.08[#/sec](mean)  ##每秒多少请求，这个是非常重要的参数数值，服务器的吞吐量
Time per request:       92.757[ms](mean)  ##用户平均请求等待时间
Time per request:       0.928[ms](mean, across all concurrent requests)  ##服务器平均处理时间，也就是服务器吞吐量的倒数
Transfer rate:          201.09[Kbytes/sec] received  ##每秒获取的数据长度
Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    1   0.8      1       5
Processing:     2   87  18.2     93     105
Waiting:        1   46  27.0     44     101
Total:          2   88  18.2     94     106

Percentage of the requests served within a certain time (ms)
  50%     94  ## 50%的请求在94ms内返回
  66%     97
  75%     98
  80%     99
  90%    100
  95%    102
  98%    103
  99%    104
 100%    106 (longest request)
```
  




