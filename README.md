# build-vue
搭建vue



在官网下载node-v6.10.1-x64.msi的安装包直接安装，
可更改安装路径，node环境会自动配好，但npm的全局安装路径还是默认，
这样会找不到用npm安装的包，例如：
$ vue -v
bash: vue: command not found


方法一：（百度到的，不过对我无效....）
在G:\nodejs下增加文件夹npm_global_modules
打开 ’nodejs安装目录/node_modules/npm/.npmrc‘  ，修改此文件为：
prefix = G:\nodejs\npm_global_modules
好了，试一下 npm install bootstrap -g 是否安装在了指定目录呢？
如果此方法对你无效，可以试下第二种方法！
方法二：
1、打开终端，执行npm config ls
2、修改prefix的值：npm config set prefix “G:\nodejs\npm_global_modules”
     需要双引号

再到用户环境PATH，看npm的路径是否为G:\nodejs\npm_global_modules
如果还在C盘就更改

完成！

如果不想那么复杂全部按默认安装就可以了

=====================================================
=====================================================

一、 安装 node.js

首先需要安装node环境，可以直接到中文官网http://nodejs.cn/下载安装包。

只是这样安装的 node 是固定版本的，如果需要多版本的 node，可以使用 nvm 安装http://blog.csdn.net/s8460049/article/details/52396399

安装完成后，可以命令行工具中输入 node -v 和 npm -v，如果能显示出版本号，就说明安装成功。

二、安装 vue-cli

安装好了 node，我们可以直接全局安装 vue-cli：

npm install -g vue-cli
但是这种安装方式比较慢，推荐使用国内镜像来安装，所以我们先设置 cnpm：

npm install -g cnpm --registry=https://registry.npm.taobao.org
如果安装失败，可以使用 npm cache clean 清理缓存，然后再重新安装。后面的安装过程中，如有安装失败的情况，也需要先清理缓存

同样可以使用 cnpm -v 查看是否安装成功

然后使用 cnpm 安装 vue-cli 和 webpack

cnpm install -g vue-cli
最新的 vue 项目模板中，都带有 webpack 插件，所以这里可以不安装 webpack

安装完成后，可以使用 vue -V （注意 V 大写）查看是否安装成功。

如果提示“无法识别 'vue' ” ，有可能是 npm 版本过低，可以使用 npm install -g npm 来更新版本

