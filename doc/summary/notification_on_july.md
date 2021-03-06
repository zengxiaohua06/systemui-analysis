# Notification功能需求与设计实现文档

内容：
* 项目简介
* 功能需求

* 项目进展
* 存在问题
* 设计实现


# 项目简介
　本项目属于Openthos开源项目的子项目，主要是基于Android SystemUI里面的Notification功能，x86 PC机器的用户实际应用场景，进行界面的深度定制和功能拓展。11月的工作主要是维护和fix bug.

##　当前开发人员 (20161101-20161130)
曹永韧

##　当前开发人员 (20160801-20160831)
刘畅

# 功能需求
| 序号 	| 功能	| 类型 	| 进度 |
| ----- | ---- | ----- |----- |
| 1 | 通知中心 | 界面 |  50% |
| 2 | 通知管理 | 界面- | 50% |
| 3 | 清除所有 | 界面 |50% |
| 4 | 打印信息 | 界面 | 80% |
| 5 | 打印任务管理 | 界面 | 80% |
| 6 | 截屏 | 界面 | 50% |
| 7 | 隔离模式 | 界面 | 50% |
| 8 | 投影 | 界面 | 50% |
| 9 | 设置 | 界面 | 100% |
| 10 | 靠右边贴屏 | 功能 | 100% |
| 11 | 通知中心 | 功能 | 50% |
| 12 | 通知管理 | 功能 | 0 |
| 13 | 清除所有 | 功能 | 0 |
| 14 | 打印信息 | 功能 | 100% |
| 15 | 打印任务管理 | 功能 | 100% |
| 16 | 截屏 | 功能 | 50% |
| 17 | 隔离模式 | 功能 | 0 |
| 18 | 投影 | 功能 | 80% |
| 19 | 设置 | 功能 | 100% |

# 8 月需求
- 1.中英文文字
- 2.图标要一致
- 3.文字的大小要一致
- 4.文字的位置
- 5.通知管理功能
- 6.清除所有功能
- 7.截屏功能
- 8.投影功能
- 9.隔离模式

# 8 月计划
| 序号 	| 功能	   | 计划时间节点 	|
| ----- | ------- | ------------- |
| 1 | 中英文文字 |  8月３日 |
| 2 | 图标要一致 |　8月4日 |
| 3 | 文字的大小要一致| 8月8日　|
| 4 | 文字的位置 |　8月8日　|
| 5 | 通知管理功能 | 8月11日 |
| 6 | 清除所有功能 | 8月12日 |
| 7 | 投影功能 | 8月16日 |
| 8 | 截屏功能 | 8月22日 |
| 9 | 隔离模式 | 8月26日 |

# 11月份任务计划
| 时间节点 | 任务 
|---|---|
|2016/11/1-2016-/11/30 |本月主要任务为：实现投影的自定义Dialog和实现通知管理,解决最新openthos使用发现影响性能优先级高的bug <br />任务分配如下：[work_plan.md](https://github.com/openthos/systemui-analysis/blob/master/dongpeng/work_plan.md) <br />

# 项目进展


## 前期
- 陈刚
  * 了解清楚通知栏的大概实现原理，然后更改布局（从上方更改到右下方）。
  * 并把显示和隐藏的机制进行改进，以适合多窗口的情况。
  * 对于通知消息以及相关的滚动布局，进行了一定的定制。
    * 时间：１周

## 后期
- 北京大学学生屈中山
  * 参与对布局和快速设置部分进行了优化；
  * 增加和删减各个相关的功能。
    * 时间：2周

- 北京工业大学学生罗浩
  * 解决了一些相关的bugs，例如：
  * 显示与隐藏时的一些问题
  * 锁屏
  * 与通知栏之间相互影响的问题等。
    * 时间：2周


# 存在问题
| 简述  | 类别  | Url链接地址 |
| ---- |------- |:---------|
| 通知栏中弹出的通知呈重叠式出现 | bug | https://dev.openthos.org/zentao/zentao/bug-view-26.html |
| 通知栏有通知显示时，最顶端仍显示“ 没有通知” | bug | https://dev.openthos.org/zentao/zentao/bug-view-38.html |
| 20160616-4-eng版本, 通知栏四个按钮有两个无图标.需增加 | bug |	https://dev.openthos.org/zentao/zentao/bug-view-99.html |
|  WIFI开启时，通知栏弹出区域有框无AP列表，需等待一会AP列表才会显示出来（刷新存在问题） 	| bug | https://dev.openthos.org/zentao/zentao/bug-view-126.html　 |　


# 主要的困难和问题：
通知栏部分的代码，在详细设计上存在一些问题，导致较简单的功能，实现代码却非常缠绕，而且消息也相互关联很紧，
由此导致对其进行定制更改时，要明显比一般的窗口程序复杂的多。


# 设计实现
