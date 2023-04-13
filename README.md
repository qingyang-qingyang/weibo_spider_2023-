# weibo_spider_2023
一个简单的微博爬虫
- -*- coding:       utf-8 -*-
- author:           qingyang
- 运行环境           Python3.9.6/windows/jupyter notebook
- 参考              月小水长https://github.com/inspurer
- github            https://github.com/qingyang-qingyang/weibo_spider_2023-
***
### 文件GetWeiboTopicData.ipynb
某个时间段内微博主题爬虫，包含微博信息获取和用户信息获取两个小功能
##### **思路**
- 在微博话题页可以拿到当页微博的html小块，直接用xpath可以得到user_id和mblog_id，以及非转发的微博正文（包括需要展开的长微博）
- 通过这两个id可以得到用户主页link和某条微博原始link
- 在某条微博原始链接下爬取微博信息（包括微博正文和转发的微博原文）
- 在用户主页link可以拿用户信息
##### **功能**
- 获取用户info
   - 昵称
   - 性别
   - IP地址
   - 粉丝数
   - 关注数
- 获取微博信息
  - 发布者主页链接
  - 微博原始链接
  - 发布者`user_id`
  - 微博识别码`mblog_id`
  - 是否原创微博
  - 微博正文
  - 转发原文（未经处理
  - 发布位置
  - 发布时间
  - 点赞数
  - 转发数
  - 评论数
  
##### *可能存在的BUG*
(已修改完成，该BUG解决2023.4.13）
描述：爬取时间段可能发生冲突，即规定时间段内可能没有那么多页
解决：时间段优先级高于页数
