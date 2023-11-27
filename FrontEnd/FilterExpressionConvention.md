
### 逻辑

| 标识符 | 说明  |                                     语法                                     | 例子  |
| :----: | :---: | :--------------------------------------------------------------------------: | :---: |
|  $and  |  与   | { $and: [ { <expression1> }, { <expression2> } , ... , { <expressionN> } ] } |       |
|  $or   |  或   |                { field: { $not: { <operator-expression> } } }                |       |
|  $not  |  非   |  { $or: [ { <expression1> }, { <expression2> }, ... , { <expressionN> } ] }  |       |
|  $nor  | 或非  |  { $nor: [ { <expression1> }, { <expression2> }, ...  { <expressionN> } ] }  |       |

### 比较

| 标识符 |   说明   |                           语法                           | 例子  |
| :----: | :------: | :------------------------------------------------------: | :---: |
|  $eq   |   等于   |                { field: { $eq: value } }                 |       |
|  $gt   |   大于   |                { field: { $gt: value } }                 |       |
|  $lt   |   小于   |                { field: { $lt: value } }                 |       |
|  $ne   |  不等于  |                { field: { $ne: value } }                 |       |
|  $gte  | 大于等于 |                { field: { $gte: value } }                |       |
|  $lte  | 小于等于 |                { field: { $lte: value } }                |       |
|  $in   |   包含   | { field: { $in: [<value1>, <value2>, ... <valueN> ] } }  |       |
|  $nin  |  不包含  | { field: { $nin: [ <value1>, <value2> ... <valueN> ] } } |       |

### 示例

````te
 {"fieldName1":1,"fieldName2":"2"}                                                             field1 = 1 AND fieldName = '2'
 {"fieldName1":{"$gt":1}}                                                                      fieldName1 > 1
 {"$and":[{"a":1},{"$or":[{"b":2},{"c":3}]}]}                                                  (a = 1) AND (b = 2 OR c = 3)
 {"nor":[{"a":1},{"b":{"$gte":8}}]}                                                            NOT((a = 1) OR (b >= 8))
 {"aaa":{"$in":[1,2,3]}}                                                                       aaa IN(1,2,3)
 {"aaa":{"$nin":[1,2,3]}}                                                                      aaa NOT IN(1,2,3)
````


