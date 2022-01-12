1.Mapping - 类似数据库中的schema的定义

- 定义索引中的字段名称
- 定义字段的数据类型
- 字段，倒排索引的相关配置

2.字段的数据类型

- 简单类型
  - Text / Keyword
  - Date
  - Integer / Floating
  - Boolean
  - IPv4 & IPv6
- 复杂类型 - 对象和嵌套对象
  - 对象类型/嵌套类型
- 特殊类型
  - geo_point & geo_shape / percolator

3.Dynamic Mapping - 推断字段类型

- 在写入文档的时候，如果索引不存在，会自动创建索引
- 但是有时候会推断的不对

4.控制Dynamic Mappings

```
PUT index_name
{
	"mappings": {
		"_doc": {
			"dynamic":"false"
		}
	}
}
```

- true，文档可索引，字段可索引，Mapping被更新；
- false，存在新增字段的数据写入，该数据可以被索引，但是新增的字段被丢弃；
- strict，数据写入直接报错。



