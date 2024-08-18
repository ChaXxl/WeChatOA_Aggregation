# WeChatOA_Aggregation
微信公众号聚合平台，获取多个公众号的博文进行筛选、过滤，使用户更方便的读取公众号上的所有文章

## 关于token和cookie
进入微信公众平台，扫码登录后在网页地址栏最后面就可以看到`token=xxxxxxxxx`，
进入之后点击图文消息创建新文章，此时按F12点Network监控网络请求，点击上方超链接就会出现新请求，
随便点击一个在Header里就可以找到Cookie，将其复制到id_info.json里就可以

## TODO
- [x] 根据标题筛选可能相似博文，再获取具体内容计算重复率去重，去除大量转载文章
- [ ] 去除广告等无用博文
- [x] 定期爬取，每天早上8:00爬。爬取当前早上6:00到昨天早上6:00的
  - 需要架设服务器，当前支持终端运行`daily_update.sh`文件获取最新文章，我直接上传到hexo博客上，可根据自己需求更改sh文件
- [x] cookie和token过期自动模拟登陆获取
- [x] 已读取的文章定期检测是否博文已删除
- [x] 爬取次数限制，记录最新爬取时间，若一天内爬取过跳过，反复执行直到爬取完成
- [x] github pages搭建个人博客，将公众号聚合平台部署上去（简易版）：https://zejuncao.github.io/
- [ ] 请求频率限制时，切换代理ip

## 类似项目参考
- https://github.com/jooooock/wechat-article-exporter
- https://github.com/1061700625/WeChat_Article