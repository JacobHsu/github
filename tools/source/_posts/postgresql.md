---
title: PostgreSQL
---

## PostgreSQL 指令  

顯示所有資料庫 	 `\l`
切換資料庫	 `\c <資料庫名稱>`
查看表	 `\dt`
查看表結構 	 `\d`
查看索引	 `\di`
查看某個表的狀況 	 `\d [表名]` 
查看所有用戶	 `\du`
 	 
結束	`\q`

`postgres=# \dt;`  

## PostgreSQL RESTful
[使用postgrest全自動生成面向表的RESTful接口](https://www.kankanzhijian.com/2018/10/10/postgrest/)  

嘗試使用了一下postgrest，用法非常簡單，但是功能非常強大。不僅能生成相應的`RESTful接口`，更是連`swagger`文檔都給準備好了，簡直意外驚喜。關於使用，如果有docker經驗的話  

[PostgREST](https://postgrest-docs-chinese.readthedocs.io/zh/latest/tutorials/tut0.html)  

[安裝 Docker for Windows](https://skychang.github.io/2017/01/06/Docker-Docker_for_Windows_10_First/)  
[Get started with Docker for Windows](https://docs.docker.com/docker-for-windows/) 

[Windows 10安装Docker 报 `Hardware assisted virtualization and data execution protection must be enabled`](https://my.oschina.net/u/2289161/blog/1647017)

