tutorial01 和tutorial02 讲解了框架自带的实现分表路由规则。本章将讲述如何根据自己的需求扩展自己的分表分库路由。

# 接口说明 #
扩展自己的分表分库规则前，先看一张继承类图：<br />
![http://img04.taobaocdn.com/bao/uploaded/i4/14839042866824365/T1UxEQFjhdXXXXXXXX_!!723064839-2-pix.png_570x10000.jpg](http://img04.taobaocdn.com/bao/uploaded/i4/14839042866824365/T1UxEQFjhdXXXXXXXX_!!723064839-2-pix.png_570x10000.jpg)
<br />
  * IRWRoute接口：
只关注读写路由规则，
从此接口可以获取读写信息。

  * IDBRoute接口：
只关注分库分表规则，
从此接口可以获取分库分表信息。

  * IRoute接口:
对两接口做汇总。

  * AbstractRoute抽象类:
继承于IRoute，做了Route大众属性的实现，继承改类后
只需实现自己的parseRouteConfig、getDBGroupName、getTableName方法

##  ##