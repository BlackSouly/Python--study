Python网络爬虫相关学习

爬虫：按照一定的规则，自动抓取网络信息的程序或脚本

使用库：requests,BeautifulSoup,正则表达式等相关使用

爬取整个页面相关代码：

`import requeests`

`import bs4`

`import re`

`html = urlopen('www.******.com')`

`bs = BeautifulSoup(html)`

爬虫爬取某网页图片的相关关键代码

`html = openurl('www.*****.com')`

`bs = BeautifulSoup(html)`

`images = bs.findall("img",{"src":re.compile("\.\.\/img\/gifts\/img.*\.jpp")})`

`for image in images:`

`         print(image["src"])`

在beautifulsoup中注意find（）函数以及findall（）函数的区别，如果涉及范围的情况下，则使用findall（）函数，有相关的参数控制，如果

不涉及范围则两者均可使用，要注意关键字的划定，关键字相当于与，而标签相当于或的作用。

为防止IP在测试过程中被禁用，可以使用代理IP

`def open_url(url):
    # 使用代理
    # proxies = {"http": "127.0.0.1:1080", "https": "127.0.0.1:1080"}
    headers = {
        'user-agent': 'Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/57.0.2987.98 Safari/537.36'}

    # res = requests.get(url, headers=headers, proxies=proxies)
    res = requests.get(url, headers=headers)
    
    return res`
    
    