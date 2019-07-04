<h1 align="center">kcreact工具文档使用说明</h1>

>Note:git相关内容使用说明，先保证使用前，全局安装k-kcreact-cli
```
npm i k-kcreact-cli -g
```

## 涉及功能及用途

涉及到多人协作开发公共业务组件时，产生的一系列繁琐提交及拉取操作，设计此工具以便携流程，更好提升编码外的效率。

运用 node 及 git 稀疏检出来实现工具的命令在终端上正常运行

## 拉取单个组件命令

#### kcreact pull
执行流程
- 步骤一：在cmd窗口执行命令

```js
kcreact pull
```
- 步骤二：提示用户输入要拉取的组件名，并对组件名进行校验
- 步骤三：校验本地是否有 `.git` 文件，无则创建，有则修改git拉取目录
>Note:这里修改拉取目录来保证，拉取的工作区文件为用户想要拉取的组件
- 步骤四：脚本自动修改完git拉取目录后，进行正常拉取，拉取文件为步骤二输入的组件名，空则停止脚本
- 步骤五：拉取成功，工作区为原有文件+拉取的组件

<img src="./img/kcreact_pull.png?width=890">

## 提交单个组件命令

#### kcreact commit <name>
```js
kcreact commit <name>
```
执行流程
- 步骤一：匹配执行目录是否在code下级
- 步骤二：获取版本号并检查package的版本号
- 步骤三：修改package的版本号判断是否成功
- 步骤四：创建文件是否成功
- 步骤五：执行git提交
>Note:若存在远程仓库有文件未拉取，则自动拉取文件，待用户修改完成，手动进行git commit 及 push 操作

<img src="./img/kcreact目录结构.png?width=890">




