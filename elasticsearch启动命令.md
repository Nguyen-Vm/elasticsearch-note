elasticsearch的文件目录结构

- bin，脚本文件，包括启动，安装插件等
- config，集群配置文件
- JDK，Java运行环境
- data，path.data，数据文件
- lib，Java类库
- logs，path.log，日志文件
- modules，包含所有ES模块
- plugins，包含所有已安装插件



JVM配置

- 修改JVM - config/jvm.options
  - 7.1下载的默认设置是1GB
- 配置的建议
  - Xmx和Xms设置成一样
  - Xmx不要超过机器内存的50%
  - 不要超过30GB



查看已安装插件

```
bin/elasticsearch-plugin list
```

安装插件

```
bin/elasticsearch-plugin install analysis-icu
```



启动elasticsearch实例

```
bin/elasticsearch -E node.name=node1 -E cluster.name=clustername -E path.data=node1_data -d
```

启动3节点的elasticsearch集群

```
bin/elasticsearch -E node.name=node1 -E cluster.name=clustername -E path.data=node1_data -d
bin/elasticsearch -E node.name=node2 -E cluster.name=clustername -E path.data=node2_data -d
bin/elasticsearch -E node.name=node3 -E cluster.name=clustername -E path.data=node3_data -d
```

