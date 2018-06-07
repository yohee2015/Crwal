# weibo_user_info
用scrapy的crawlspider和cookie池爬取微博用户信息

1 该爬虫爬取的是微博移动端，爬虫的方式是从某个用户出发，利用scrapy的LinkExtractor不断抽取用户关注列表和用户粉丝列表的连接并爬取,起始爬取用户可到settings文件中配置

2 存储方式采用mysql，并采取了基于异步的存储方式，需要到settings文件中配置MYSQL_PARAMS参数

2、cookie池采用了https://github.com/Germey/CookiesPool的配置，其中有三个开关，分别是cookie产生器，cookie验证器，api接口，产生cookie时需要确保redis数据库中已经放入了相应的账户，测试时可将自己的账户放入其中，并将产生器开关打开，产生cookie以后可以将cookie验证期打开，以验证cookie的有效性，打开api接口可以获取到随机的cookie，其中打开和关闭是指将相应的参数设置为True或False

3、cd 到 CookiesPool下运行run.py即可将cookiepool架构运转起来

4、运行main.py，即可启动微博爬虫
