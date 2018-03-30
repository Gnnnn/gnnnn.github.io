---
layout: post
title: "Common Git Command"
date: 2017-06-22
excerpt: "In case I fogot.Also,offer help to newbies."
tags: [list, git]
comments: true
---

其实就是5个步骤： 
进入你的项目的目录下：

## Tables
|number|git                        |description                 |
|:-----|:------------------------: |---------------------------:|
|1     |git init                   |
|2     |git add .readme.txt        |add the file you want       |
|3     |git commit -m ''           |'description'               |
|4     |git remote add origin url  |+your repo weburl           |
|5     |git push origin maseter    |+your repo weburl           |
|=====
| Foot1   | Foot2   | Foot3
{: rules="groups"}


## Tables

| number  | git command | description |
|:--------|:-----------:|------------:|
| cell1   | cell2       | cell3       |
| cell4   | cell5       | cell6       |
| cell1   | cell2       | cell3       |
| cell4   | cell5       | cell6       |
|=====
| Foot1   | Foot2   | Foot3
{: rules="groups"}


## 如果push报错,可以先用pull来解决eror，在重新push一下就好了.
### git command:
* git pull origin master --allow-unrelated-histories
