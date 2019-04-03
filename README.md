# Vue组件和localStorage评论列表(小dome)

###    分析发表评论的业务逻辑:
####   1.评论数据存到localStorage中 localStorage.setItem
####   2.先组织出一个最新的评论数据对象
####   3.想办法，把第二部中得到的评论对象，保存到localStorage中:
     3.1  localStorage 只支持存放字符串数据，要先调用JSON.stringify
     3.2  在保存最新的评论数据之前，要先从localStorage获取到之前评论的数据（string）转换为一个 数组对象 然后把最新的评论，push到这个数组
     3.3  如果获取到的localStorage中的评论字符串，为空不存在，则可以返回一个‘[]’让JSON.parse去转换
     3.4  把最新的评论列表数组，再次调用JSON.stringify转为数组字符串，然后调用localStorage.setItem()
