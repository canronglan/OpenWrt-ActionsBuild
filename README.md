# 使用github的Actions功能自动编译OpenWRT固件

## 仓库说明
### 1.多脚本自定义编译
- [创建路由资源目录](#创建路由资源目录)
- [路由资源目录各文件作用](#路由资源目录各文件作用)
- [如何编译OpenWRT固件](#如何编译OpenWRT固件)

### 2.配置 自动/手动 更新Actions功能(.github/workflows/内的yml脚本)
- [创建仓库环境变量(必要)](#创建仓库环境变量)
- - [GIT_TOKEN](#GIT_TOKEN)
- - [GIT_UNAME](#GIT_UNAME)
- - [GIT_UEMAIL](#GIT_UEMAIL)
- [创建可更新的yml脚本](#创建可更新的yml脚本)
- [更改自动更新时间](#更改自动更新时间)
- [关于 UpdateActionsData.sh 脚本](#关于 UpdateActionsData.sh 脚本)

## 详细内容

### 创建路由资源目录
1.在仓库的主目录下创建一个文件夹(建议使用路由型号命名，以便于区分)

2.把需要的文件和脚本放置到文件夹内，具体参考 - [路由资源目录各文件作用](#路由资源目录各文件作用)

  注意:
  
       其中的 .config 文件为必须文件，请自行配置并上传，
  
       其他文件如过无需替换或执行，可不上传或者在执行Actions时将对应的选项选择为 false
  
### 路由资源目录各文件作用

1. .config(必须) 此文件为定制路由及其插件的配置文件，必须存在路由资源目录内，可修改不同名称，但必须在Actions执行编译时，一并修改
   例如：.config文件名为 openwrt.config ,则Actions编译时 config 文件名称 项 也要修改，![image](https://user-images.githubusercontent.com/35430449/152682115-ded3d6d2-f08c-4f82-aefc-e320d191a0dd.png)
