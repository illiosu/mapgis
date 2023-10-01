## 0. 代码运行的前置条件

> #### **系统怎么跑起来？</u>**

> 1. 配置mongoDB数据库环境（可本地安装mongodb compass,会默认安装本地数据库，localhost:27017连接数据库，创建vue_webgis/users，运行程序后注册用户即可登录），也可选择线上mongodb数据库，修改config中数据库连接配置即可。
> 2. cd client
> 3. npm install (客户端代码中安装依赖)
> 4. cd ../
> 5. npm install (服务端代码中安装依赖)
> 6. npm run dev (前后端连载，同时启动前后端)

## 1. 效果展示
**系统登陆**
![loginPage.png](https://i.loli.net/2021/11/17/reFpu5ABTdi8zoX.png)

---

**地图首页，支持Google，天地图，高德，腾讯，Geoq，Arcgis等多源在线网络地图的切换**
> Google地图公共影像已下架（2021年1月）
> 调整原有代码view与components的混乱；MapBox地图组件封装，数据图层加载组件，地图底图切换组件；（2021.1.31）

![mapHomePage.png](https://i.loli.net/2021/11/17/fSaKQCoZXeH3uzJ.png)

---

**3维建筑物地图，基于MapBoxGL加载GeoServer三维建筑物矢量切片**
![3Dbuilding.png](https://i.loli.net/2021/11/17/NYyTzPI2LD4cURE.png)

---

**MapBox自定义底图**
![mapbox01.png](https://i.loli.net/2021/11/17/3eMyHIYaRXp6FfV.png)

---
**MapBoxgl绘制**
![mapbox_draw.png](https://i.loli.net/2021/11/17/6JMmO9l2QHEuvVN.png)

---
**MapBoxGL集成deck.gl实现高性能可视化**
![HexgonMap.png](https://i.loli.net/2021/11/17/8qBGaTFMpy6Z7HX.png)

---

**openlayers聚合图**
![openlayerCluster.png](https://i.loli.net/2021/11/17/lR9tv6hEbdAXDJK.png)

---
**openlayers裁剪地图底图**
![openlayerClip.png](https://i.loli.net/2021/11/17/ilWN9UVp7hSewat.png)

---

<!--系统中还有好多好玩的功能等你去发现咯-->
**arcgis api 4.x**
![arcgisHomePage.png](https://i.loli.net/2021/11/17/OCAEdesBVj4Rg7v.png)

<!--后续地图功能正在逐步完善，将尝试使用多种 map api 和集成 gis 相关库-->

##  2. VUE + Node + WebGIS项目说明：

### 2.1 实践目的：基于VUE框架使用模块化编程方式实现WebGIS的开发

### 2.2 主要功能
1. 前后端项目搭建
2. 登录注册（token验证功能）
3. 丰富的地图开发api DEMO集成，地图可视化实现

### 2.3 主要技术

> 地图框架：MapBoxGL/openlayers 5.x / ArcGIS  API 4.x

> 构建接口文档：Node + express + jwt;

> 构建前端页面：VueCli 3.0 + ElementUI

> 数据请求及拦截：Axios + MongoDB

> 其他即将或已经使用的技术：GeoServer, PostGIS, deck.gl, echarts, 

### 2.4 项目的搭建细节

#### （1）准备工作
1.1 搭建服务器（基于express）

1.2 连接本地的MongoDB数据库

1.3 搭建路由和数据模型

#### （2）登录注册接口
> express的body-parser中间件

> bcrypt加密模块

> jsonwebtoken

获取token(获取数据的令牌/jsonwebtoken)-----验证token（passport/passport-jwt）


#### （3）Passport验证



#### （4）前后端连载
