1.使用_analyzer API

- 直接指定Analyzer进行测试

```
GET /_analyze
{
	"analyzer":"standard",
	"text":"Elasticsearch Note"
}
```

- 指定索引的字段进行测试

```
POST index_name/_analyze
{
	"field": "title",
	"text": "Elasticsearch Note"
}
```

- 自定义分词器进行测试

```
POST /_analyze
{
	"tokenizer":"standard",
	"filter":["lowercase"],
	"text":"Elasticsearch Note"
}
```



2.常见的分词器

Standard Analyzer

- 默认分词器
- 按词划分
- 小写处理

Simple Analyzer

- 按照非字母切分，非字母的都被去除
- 小写处理

Stop Analyzer

- 相比Simple Analyzer
- 多了stop filter，会把the，a，is等修饰性词语去除

Keyword Analyzer

- 不分词，直接将输入当一个term输出

Pattern Analyzer

- 通过正则表达式进行分词
- 默认是\W+，非字符的符号进行分隔



3.中文分词

icu analyzer，ik，thulac