# weibo-video-monitoring
weibo Video resource dynamic monitoring
动态监听微博视频资源

只需传入一个微博视频地址
比如：
https://m.weibo.cn/status/4429523514607767?sourceType=qq&from=1099195010&wm=20005_0002&featurecode=newtitle

保证每次返回的都是有效的视频地址

# 系统设计
- 2级cache
    -  微博地址缓存:视频真实地址缓存  自定义过期时间  (推荐24h)  写加锁防止并发请求
    -  每次用户访问 检测是否过期时间 推荐(5min) 写加锁防止并发请求
