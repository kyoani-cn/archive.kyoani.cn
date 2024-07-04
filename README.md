# 京阿尼相关网站通用 备份、翻译 工具

地址 archive.kyoani.cn

## 路径规划
基础上参考 web.archive.org 路径规则
在网页中记录路径的完整地址、抓取时间、语言版本
尽可能实现全站静态化，可能的话基于 GitHub 实现这个功能
可能的话路径规划实现成和文件目录一致

```base
# 首页
https://archive.kyoani.cn/

# 抓取
https://archive.kyoani.cn/create.html

# 实际被抓取页面展示地址

## 原始地址
https://www.kyotoanimation.co.jp/information/?id=6005

## 抓取之后的展示地址 方案一 文件目录相同
https://archive.kyoani.cn/:/kyotoanimation.co.jp/information--id=6005_202407041948/

https://archive.kyoani.cn/:/ # 为基础路径
https://archive.kyoani.cn/:/index.html # 展示被抓取的地址历史

# 历史被抓取的所有页面信息
https://archive.kyoani.cn/history.jsonl
格式为
{
  title: '7月18日現地追悼のご辞退等について - 新着情報 | 京都アニメーションホームページ',
  url: 'https://www.kyotoanimation.co.jp/information/?id=6005',
  path: 'kyotoanimation.co.jp/information--id=6005_202407041948/',
  date: '202407041948',
  catcher: 'itorr',
}
# 翻译页面 就是展示页面，但是插入翻译选项页头，点击后会在页面上展示翻译选项
https://archive.kyoani.cn/:/kyotoanimation.co.jp/information--id=6005_202407041948/

# 翻译后的数据保存在
https://archive.kyoani.cn/:/kyotoanimation.co.jp/information--id=6005_202407041948/_translation.jsonl

## 格式为 tran 新翻译 disabled 屏蔽某条翻译
[1234567890,'tran','翻译人1昵称','uuid1','原文1','译文1','zh_CN']
[1234567890,'tran','翻译人1昵称','uuid2','原文2','译文2','zh_HK']
[1234567890,'tran','翻译人1昵称','uuid3','原文2','译文2','en']
[1234567890,'disabled','操作人昵称','uuid2']


# 页面评论
https://archive.kyoani.cn/:/kyotoanimation.co.jp/information--id=6005_202407041948/_comments.jsonl

[1234567890,'comment','昵称','uuid4','评论文字','父级id']


```
