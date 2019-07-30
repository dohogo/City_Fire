# City_Fire
### 概述
&ensp;&ensp;&ensp;&ensp;本系统利用了SpringBoot和Vue实现了对城市消防监控设备的在线统计管理，系统具备区域管理、设备分类管理、设备管理、预警管理和报表统计五大功能，通过设备分类，将所有消防设备进行唯一编码，有效的满足了消防设备的在线统计查看，设备异常后报警更换，及对设备维修更换率生成报表在线查看。  
特点：<br> 
1.前后端分离，Vue实现前端模块化，后台通过SpringBoot+Mysql,保证数据的有效性和安全性。<br> 
2.动态路由菜单栏、Element-UI、高德地图Api选择地理位置、Shiro权限控制、Mybatis plus。 <br> 
3.Docker做容器，Redis实现数据缓存，Nginx+Dubbo实现负载均衡，满足消防设备异常及时同步处理、高并发，真正的满足城市甚至省级所用消防设备的在线管理。<br> 
### 演示链接：
&ensp;&ensp;&ensp;http://120.79.81.9  帐户和密码恕不告诉，有需要可以提issue，我会开放1h，因为有人一直乱改，改成了什么水电管理系统...留个联系方式（332252453）
#### 注意事项：
1. 不要修改密码，采用SHA256 加盐加密
2. 数据可以增加，不要删除我原来的数据，可以删除你新增的数据，因为毕设还没检查

### 功能：
- 首页
- 系统管理
  - 用户列表
  - 角色管理 
  - 菜单管理 （shiro）
  - sql管理 （druid monitor )
  - 定时任务 （目前没用）
  - 参数管理 （目前没用）
  - 文件上传 （待开发）
  - 系统日志 
- 地区管理
  - 新增地区：vue-amap,实现模糊搜索定位选择地区(发现一个问题，amap中搜索范围我只限定了成都,省信息直接默认填四川028)
  - 所有地区：分页，支持模糊搜索、按条件搜索，备注、禁用恢复
  - 导出：    APache POI
- 分类管理 ：因为类别不多，采用单表不分页，如果是考虑分页的话，两张表更好，增加关系表，el-tree,级联更新
- 设备管理 ：新增设备，rule限制规则，尽量让用户选择而不是输入，设备编码老师说尽量的长且唯一，所以采用生成编码的方式
  - 新增地区：vue-amap,实现模糊搜索定位选择地区
  - 设备列表：分页，支持模糊搜索、按条件搜索
- 统计管理 ：
  - 位置统计：按成都市，区分类进行统计，各区系统拥有的地区数量（饼图）
  - 设备统计：折线图，按小区进行分类统计，横坐标为时间，纵坐标为设备数量，可通过选择时间对数据进行筛选

### 部署
前端： nginx  
后台： Tomcat9.0
数据库： mysql

### 接下来还要做的
#### 功能
1. 可能考虑增加设备报修、处理流程（可能会做成微信小程序）
2. 对设备报修率、损坏率进行图标统计
3. 修改用户头像
#### 其他
缓存 ：redis(还没想好缓存什么)<br>
部署： Dubbo+Zookeeper+Nginx 集群和负载均衡（2月会学，尽量会用到系统中来，尽管我觉得不需要）<br>
后台： 使用 Docker 部署 Springboot 应用<br>
