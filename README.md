# City_Fire
本系统利用了SpringBoot和Vue实现了对城市消防监控设备的在线统计管理，系统具备区域管理、设备分类管理、设备管理、预警管理和报表统计五大功能，通过设备分类，将所有消防设备进行唯一编码，有效的满足了消防设备的在线统计查看，设备异常后报警更换，及对设备维修更换率生成报表在线查看。  技术：  1.系统实现了前后端分离，利用Vue实现前端模块化，后台通过SpringBoot+Mysql,保证数据的有效性和安全性。  2.满足区域管理、设备分类管理、设备管理、预计管理和报表统计五大功能。  3.系统利用Docker做容器，Redis实现数据缓存，Nginx+Dubbo实现负载均衡，满足消防设备异常及时同步处理、高并发，真正的满足城市甚至省级所用消防设备的在线管理