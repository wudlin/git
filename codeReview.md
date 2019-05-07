<h1 align="center">codeReview</h1>

>note:介绍在 gitlab 上如何使用 codeReview 即 MergeRequest ,codeReview 在 gitlab 及 github 中有不同的名称,gitlab 为 MergeRequest , github 为 PullRequest

## 目录
- [设置保护分支](#设置保护分支)
    - [打开gitlab中的项目](#打开gitlab中的项目)
    - [Protected Branches 进行设置](#Protected-Branches-进行设置)
- [发起MergeRequest](#发起MergeRequest)
    - [进行merge request](#进行merge-request)
- [审查人员界面](#审查人员界面)
- [codeReview流程图](#codeReview流程图)

## 设置保护分支

#### 打开gitlab中的项目
在项目中找到branches(分支),中有 `project settings.` 

<img src="./img/mr1.png?width=890">

#### Protected Branches 进行设置
在 `project settings.` 列表中找到 `Protected Branches` 进行设置

<img src="./img/mr2.png?width=890">

## 发起MergeRequest

#### 进行merge request
在项目中找到branches(分支)

<img src="./img/mr3.png?width=890">

在项目中找到branches(分支),中有 `MergeRequest`

<img src="./img/mr4.png?width=890">

短暂的等待后进入 `MergeRequest` 设置界面
>note:这里合并的目标默认是在 master 需要手动更改

<img src="./img/mr5.png?width=890">


## 审查人员界面
>note:这里如果无代码冲突 `Merge` 按钮为可点击，有冲突则至灰。

<img src="./img/mr6.png?width=890">

>note:不论通过还是关闭 `MergeRequest` 都将通知发起人

## codeReview流程图

<img src="./img/codeRequest.jpg?width=890">

参考资料：https://blog.csdn.net/weixin_40400084/article/details/81450553
