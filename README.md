# Tsinghua-CourseSpider

用于清华大学选课系统的爬虫及基于MS Excel的选课工具

# 构成
## OpeningInfo.py
核心文件，运行即爬去数据并存到`OpeningInfo.xlsx`中。

## OpeningInfo.xlsx
存储开课信息的表格，结构基本与选课系统上的表格一致。

## 课表安排.xlsm
其中表`课程信息`内容通过MS Excel Query读取`OpeningInfo.xlsx`中的数据并添加`课程ID`字段。
在表`课表`中修改`课程ID`部分，自动填充其他内容。

# 使用方法
克隆本仓库，安装`pandas`、`lxml`库。
* 修改`OpeningInfo.py`
    * `xq`字段，根据需要爬取的学期修改
    * `token`字段，此字段值从浏览器的请求中抓包获取
    * `headers`中的`Cookie`字段，从浏览器请求中抓包获取
运行`python OpeningInfo.py`，待完成后即自动更新`OpeningInfo.xlsx`文件，`课表安排.xlsm`中的课程信息应当自动修改，按需要选课即可。

# TODO
给`课表安排.xlsm`添加VBA宏，使用更方便。
