<h1 align="center">husky</h1>

## 注册 git hook

#### 安装：husky
```js
npm i --save-dev husky@1.2.0 lint-staged
```

#### 关于 husky 版本问题
>Note:如果使用 1.3.0 会出现 `git push` 后无反应的情况，建议使用 `1.2.0` 
```js
    "husky": "1.2.0",
```


修改 `package.json` 

```diff
 "scripts": {
    ···
+   "precommit": "lint-staged"
  },
+ "lint-staged": {
+   "src/**/*.{js,jsx}": [
+     "prettier --single-quote --tab-width 4 --write",
+     "eslint --fix",
+     "git add"
+   ]
+ },
```

- tab-width 4:使用4个空格作为缩进
- write：默认prettier是直接标准输出到终端的，这个配置代表直接改写文件
- single-quote：使用单引号


## 实现过程
- 待提交的代码
- git add 添加到暂存区
- 执行 git commit
- husky注册在git pre-commit的钩子调起 lint-staged
- lint-staged 取得所有被提交的文件依次执行写好的任务（ESLint 和 Prettier）
- 如果有错误（没通过ESlint检查）则停止任务，等待下次commit，同时打印错误信息
- 成功提交

<img src="https://github.com/wudlin/git/blob/master/img/git_husky.png" alt="提交截图"/>
