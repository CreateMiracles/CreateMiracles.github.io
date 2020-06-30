---
title: 使用git命令一键发布文章
date: 2020-06-30 10:49:30
tags: hexo
---

### 一、存在问题

目前我们在windows系统中使用hexo发布文章的时候需要在指定的文件夹下，然后使用以下两条命令来发布文章，这样就使得每次的部署都非常的麻烦。

```
hexo clean
hexo g -d
```

> 注意：这里的`hexo g -d`和`hexo d -g`是等价的。

## 二、解决方案

​	这里我们可以直接使用git alias来设置一条语句执行多条命令，打开git bash，然后输入以下命令：

```
git config --global alias.bloggo '!cd C:\blog\hexo;hexo clean;hexo g -d'
```

> 注意：这里的`C:\blog\hexo`是我的博客文件夹的路径，实际使用的时候需要根据自己的路径进行修改。另外，这里的`bloggo`可以自定义其它的名字。

​	设置完成后，只需要执行`git bloggo`就可以完成一键更新博客了

## 三、如何取消别名

​	执行以下命令取消别名

```
git config --global --unset alias.bloggo
```

