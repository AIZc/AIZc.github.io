---
title: package.json详解。
date: 2021/09/15
cover: https://img2.huashi6.com/images/resource/2015/11/07/53h430426p0.jpg
categories:
- 开发
tags:
- package.json
---

## 各属性介绍：

```json
{
  "name": "myJS"
}
```
它定义了`name`属性，用于告知应用程序或软件包的名称。


这是一个更复杂的示例，该示例是从 Vue.js 应用程序示例中提取的：
```json
{
  "name": "test-project",
  "version": "1.0.0",
  "description": "A Vue.js project",
  "main": "src/main.js",
  "private": true,
  "scripts": {
    "dev": "webpack-dev-server --inline --progress --config build/webpack.dev.conf.js",
    "start": "npm run dev",
    "unit": "jest --config test/unit/jest.conf.js --coverage",
    "test": "npm run unit",
    "lint": "eslint --ext .js,.vue src test/unit",
    "build": "node build/build.js"
  },
  "dependencies": {
    "vue": "^2.5.2"
  },
  "devDependencies": {
    "autoprefixer": "^7.1.2",
    "babel-core": "^6.22.1",
    "babel-eslint": "^8.2.1",
    "babel-helper-vue-jsx-merge-props": "^2.0.3",
    "babel-jest": "^21.0.2",
    "babel-loader": "^7.1.1",
    "babel-plugin-dynamic-import-node": "^1.2.0",
    "babel-plugin-syntax-jsx": "^6.18.0",
    "babel-plugin-transform-es2015-modules-commonjs": "^6.26.0",
    "babel-plugin-transform-runtime": "^6.22.0",
    "babel-plugin-transform-vue-jsx": "^3.5.0",
    "babel-preset-env": "^1.3.2",
    "babel-preset-stage-2": "^6.22.0",
    "chalk": "^2.0.1",
    "copy-webpack-plugin": "^4.0.1",
    "css-loader": "^0.28.0",
    "eslint": "^4.15.0",
    "eslint-config-airbnb-base": "^11.3.0",
    "eslint-friendly-formatter": "^3.0.0",
    "eslint-import-resolver-webpack": "^0.8.3",
    "eslint-loader": "^1.7.1",
    "eslint-plugin-import": "^2.7.0",
    "eslint-plugin-vue": "^4.0.0",
    "extract-text-webpack-plugin": "^3.0.0",
    "file-loader": "^1.1.4",
    "friendly-errors-webpack-plugin": "^1.6.1",
    "html-webpack-plugin": "^2.30.1",
    "jest": "^22.0.4",
    "jest-serializer-vue": "^0.3.0",
    "node-notifier": "^5.1.2",
    "optimize-css-assets-webpack-plugin": "^3.2.0",
    "ora": "^1.2.0",
    "portfinder": "^1.0.13",
    "postcss-import": "^11.0.0",
    "postcss-loader": "^2.0.8",
    "postcss-url": "^7.2.1",
    "rimraf": "^2.6.0",
    "semver": "^5.3.0",
    "shelljs": "^0.7.6",
    "uglifyjs-webpack-plugin": "^1.1.1",
    "url-loader": "^0.5.8",
    "vue-jest": "^1.0.2",
    "vue-loader": "^13.3.0",
    "vue-style-loader": "^3.0.1",
    "vue-template-compiler": "^2.5.2",
    "webpack": "^3.6.0",
    "webpack-bundle-analyzer": "^2.9.0",
    "webpack-dev-server": "^2.9.1",
    "webpack-merge": "^4.1.0"
  },
  "engines": {
    "node": ">= 6.0.0",
    "npm": ">= 3.0.0"
  },
  "browserslist": ["> 1%", "last 2 versions", "not ie <= 8"]
}
```
* `version` 表明当前的版本。
* `name` 设置了应用程序/软件包的名称。
* `description` 是应用程序/软件包的简短描述。
* `main` 设置了应用程序的入口点。
* `private` 如果设置为 true，则可以防止应用程序/软件包被意外地发布到 npm。
* `scripts` 定义了一组可以运行的 node 脚本。
* `dependencies` 为代码运行时所需要的包，`会打包到线上生产环境`，像`vue、react`等这些模块是项目运行必备的，所以部署到线上的时候也要使用，应该安装在dependencies节点下，所以我们使用`-save`形式安装。
* `devDependencies` devDependencies为开发环境所需要的包，`不会打包至线上`;比如项目中使用的`gulp、webpack打包工具，压缩css、js的模块`。这些模块我们在项目部署上线后是不需要的、所以我们可以使用`-save-dev`的形式安装。
* `engines` 设置了此软件包/应用程序在哪个版本的 Node.js 上运行。
* `browserslist` 用于告知要支持哪些浏览器（及其版本）。
### 总结：
使用npm安装包的时候一定要判断好，该安装在那个节点下，实在判断不出来，那就安装在`dependencies`生产环境下，不过不建议这么做。

end～