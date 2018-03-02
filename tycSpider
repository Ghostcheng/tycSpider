#-*- coding:utf-8 -*-
import sys
from urllib.parse import quote
import requests
import urllib
from importlib import reload
import bs4

def main():    #模拟浏览器进行登录
    headers = {'Accept':'text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8' ,
                'Accept-Encoding':'gzip, deflate, br' ,
                'Connection':'keep-alive',
                #'DNT':'1',
                'Host':'www.tianyancha.com',
                'Referer':'https://www.tianyancha.com/',
                'Upgrade-Insecure-requests':'1',
                'User-Agent':'Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/64.0.3282.119 Safari/537.36'


    }

    cookies = {'ssuid':'182260751',
               'aliyungf_tc':'AQAAACPaBxKTsgwAeY9+fMuU+0hC4mMe',
               #'bannerStorageV2':'',
               #'_pk_ref.1.e431':'',
               'token':'d295f302e4cd4ebda7c4ea01fcef52c8',
               '_utm':'b4fc1a08cb30496f98f63737d1bc5e02',
               #'_pk_id.1.e431':'',
               #'paaptp':'',
               'csrfToken':'zMUTLrtQzFwPetwvv9DHRYCf',
               'TYCID':'ca3fb4f01dbc11e899e733d671ee7ec3',
               'undefined':'ca3fb4f01dbc11e899e733d671ee7ec3',
               #'uccid':'',
               'tyc-user-info':'%257B%2522token%2522%253A%2522eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIxODg0NTc4NjUxOSIsImlhdCI6MTUxOTk1ODA3MywiZXhwIjoxNTM1NTEwMDczfQ.3a6L0Lf1lpUFsjDYWoxTGCobCDbB-A0TNuPBZn8xfOpKhwL458LOY2LGXucQSqC_3VTzuiEP4QyOb4Kg83q-3A%2522%252C%2522integrity%2522%253A%25220%2525%2522%252C%2522state%2522%253A%25220%2522%252C%2522vipManager%2522%253A%25220%2522%252C%2522vnum%2522%253A%25220%2522%252C%2522onum%2522%253A%25220%2522%252C%2522mobile%2522%253A%252218845786519%2522%257D',
               'bannerFlag':'true',
               'RTYCID':'5a40dd6334d941338319c9f1d8913073',
               #'Qs_lvt_117460':'',
               #'bannerFlag':'',
               #'_csrf':'',
               #'OA':'',
               #'_csrf_bk':'',
               'auth_token':'eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIxODg0NTc4NjUxOSIsImlhdCI6MTUxOTk5MjQzOCwiZXhwIjoxNTM1NTQ0NDM4fQ.Ai2CKLjR2F47nuT3ODeXfSHu7rRFRyIw1WqWoQJj-4mISpuITax-Nec3btnYES2KXYVjVjakEf1esXMNjPMddA',
               'Hm_lvt_e92c8d65d92d534b0fc290df538b4758':'1519748112,1519955742,1519987657,1519991442',
               'Hm_lpvt_e92c8d65d92d534b0fc290df538b4758':'1519992691'

    }

   # keyWord = '深圳市腾讯计算机系统有限公司'

    startUrl = 'https://www.tianyancha.com/company/9519792'  #我们要请求的URL

    resultPage = requests.get(startUrl,headers= headers,cookies= cookies) #带着请求头信息进行模拟登陆
    # 把我们获取到的信息保存在当前目录的txt文件中
    with open('tyc_demo.txt','w',encoding='utf-8') as of:
        of.write(resultPage.text)
    #print(resultPage.text)

    #接下来使用beautifulSoup来解析出我们要的信息
    noStarchSoup  = bs4.BeautifulSoup(resultPage.text,"html.parser")   # 将我们拿到的HTML用beautifulSoup做成汤
    elems = noStarchSoup.find_all('a',class_='in-block vertival-middle overflow-width')  # 取出我们要的股东信息
    #print(elems)  # 打印验证
    print('股东信息：')
    for a in elems:  # 遍历拿出我们的结果
        print(a["title"])


# 执行程序
if __name__ == '__main__':
    reload(sys)
    main()
