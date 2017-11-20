### 训练数据（weibo_train_data）2015-02-01至2015-07-31

博文的全部信息都映射为一行数据。其中对用户做了一定抽样，获取了抽样用户**半年**的原创博文，对用户标记和博文标记做了加密 发博时间精确到天级别。 

| 字段            | 字段说明        | 提取说明    |
| ------------- | ----------- | ------- |
| uid           | 用户标记        | 抽样&字段加密 |
| mid           | 博文标记        | 抽样&字段加密 |
| time          | 发博时间        | 精确到天    |
| forward_count | 博文发表一周后的转发数 |         |
| comment_count | 博文发表一周后的评论数 |         |
| like_count    | 博文发表一周后的赞数  |         |
| content       | 博文内容        |         |

###  预测数据（weibo_predict_data）2015-08-01至2015-08-31

| 字段      | 字段说明 | 提取说明    |
| ------- | ---- | ------- |
| uid     | 用户标记 | 抽样&字段加密 |
| mid     | 博文标记 | 抽样&字段加密 |
| time    | 发博时间 | 精确到天    |
| content | 博文内容 |         |

### 选手需要提交的数据（weibo_result_data）

选手对预测数据（weibo_predict_data）中每条博文一周后的转、评、赞值进行预测

| 字段            | 字段说明        | 提取说明    |
| ------------- | ----------- | ------- |
| uid           | 用户标记        | 抽样&字段加密 |
| mid           | 博文标记        | 抽样&字段加密 |
| forward_count | 博文发表一周后的转发数 |         |
| comment_count | 博文发表一周后的评论数 |         |
| like_count    | 博文发表一周后的赞数  |         |

选手提交结果文件的转、评、赞值必须为整数不接受浮点数！注意：提交格式(.txt)：uid、mid、forward_count字段以tab键分隔，forward_count、comment_count、like_count字段间以逗号分隔

### 评估指标

对于每一条博文预测出发表一周后的转发数、评论数和赞的数目，对于每一项均和真实值计算偏差：

![valuation.png](https://github.com/ChaoZeyi/weibo_baseline/blob/master/pics/valuation.png?raw=true)

