#  Download_YouTube

> 起因：在YouTube看到一很喜欢的视频，想要下载高清格式的视频。试了谷歌浏览器插件和QQ浏览器插件都不行，只能谷歌搜索解决方案：
>
> 通过ss和proxifer实现fq和cmd_sock5代理,安装go和git，使用annie下载，后使用ffmpeg合并视频音频



- Reference
  - [shadowsocks](https://github.com/shadowsocks)
  - [proxifer](http://blackwolfsec.cc/2016/09/19/Proxifier_Shadowshocks/)
  - [go 安装](https://github.com/astaxie/build-web-application-with-golang/blob/master/zh/01.1.md)
  - [git 安装](https://github.com/xiaoxiaoc111/Tools/blob/master/Git.md)
  - [annie+ffmpeg](https://github.com/iawia002/annie#install-via-go-get)

- command

	- ```bash
		go get github.com/iawia002/annie
		annie https://youtu.be/Gnbch2osEeo
		```

- Supported Sites

	- |            |                                                           |        |        |          |                |
		| ---------- | --------------------------------------------------------- | ------ | ------ | -------- | -------------- |
		| Site       | URL                                                       | Videos | Images | Playlist | VIP adaptation |
		| 抖音       | [https://www.douyin.com](https://www.douyin.com/)         | ✓      |        |          |                |
		| 哔哩哔哩   | [https://www.bilibili.com](https://www.bilibili.com/)     | ✓      |        | ✓        | ✓              |
		| 半次元     | [https://bcy.net](https://bcy.net/)                       |        | ✓      |          |                |
		| pixivision | [https://www.pixivision.net](https://www.pixivision.net/) |        | ✓      |          |                |
		| 优酷       | [https://www.youku.com](https://www.youku.com/)           | ✓      |        |          | ✓              |
		| YouTube    | [https://www.youtube.com](https://www.youtube.com/)       | ✓      |        | ✓        |                |
		| 爱奇艺     | [https://www.iqiyi.com](https://www.iqiyi.com/)           | ✓      |        |          |                |
		| 芒果TV     | [https://www.mgtv.com](https://www.mgtv.com/)             | ✓      |        |          |                |
		| Tumblr     | [https://www.tumblr.com](https://www.tumblr.com/)         | ✓      | ✓      |          |                |
		| Vimeo      | [https://vimeo.com](https://vimeo.com/)                   | ✓      |        |          |                |
		| Facebook   | [https://facebook.com](https://facebook.com/)             | ✓      |        |          |                |
		| 斗鱼视频   | [https://v.douyu.com](https://v.douyu.com/)               | ✓      |        |          |                |
		| 秒拍       | [https://www.miaopai.com](https://www.miaopai.com/)       | ✓      |        |          |                |
		| 微博       | [https://weibo.com](https://weibo.com/)                   | ✓      |        |          |                |
		| Instagram  | [https://www.instagram.com](https://www.instagram.com/)   | ✓      | ✓      |          |                |
		| Twitter    | [https://twitter.com](https://twitter.com/)               | ✓      |        |          |                |

- to do list

	- 腾讯视频