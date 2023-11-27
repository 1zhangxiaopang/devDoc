
### 数组相关

#### getObjNameValueToArr

##### 1.功能说明

````sh
将传入对象转换为数据
  1、排除对象属性名为_XID的属性
  2、排除对象属性名包含'|' 和 '/'
````



##### 2.参数说明

````javascript
传入参数 obj : {[key: string]: any;}
返回参数 : Array<{name:string ; value:any}> | []
````



##### 3.举例

````ts
const obj : any = {_XID : 1 , 'm2o|xxx' : 2 , 'slc/xxx' : 3 , foo : 5};
const result : Array<{name:string ; value:any}> = Tsrv.utils.getObjNameValueToArr(obj);
console.log(result) //[{name:'foo' , value : 5}]
````



#### mapToArr

##### 1.功能说明

```sh
将传入Map转为数组类型
```

##### 2.参数说明

```javascript
传入：m: Map<string, any>
传出：Array<obj> | []
```

##### 3.举例

````ts
const m : Map<string,string|number> = new Map();
m.set('a',1)
console.log(Tsrv.utils.mapToArr);  //  [{a : 1}]
````



#### objToArr

##### 1.功能说明

```sh
传入obj转化为数组数据
```

##### 2.参数说明

```javascript
传入：obj: { [key: string]: any },   key: string = 'key',     value: string = 'value',    
     options?: {
       ignore?: string[];
       ignoreRegex?: string[];
      }
传出：Array<obj> 
```

##### 3.举例

````ts
需代入系统理解
````



#### EnCode

##### 1.功能说明

```sh
将传入的数据利用base64加密
```

##### 2.参数说明

```javascript
传入：str: string
传出： string 

```

##### 3.举例

````ts
const str : string = 'aaaaa';
const enCodeStr : string = Tsrv.utils.EnCode(str);
console.log(enCodeStr);//WYFhYWE=
````



#### DeCode

##### 1.功能说明

```  sh
将传入数据通过base64解码
```

##### 2.参数说明

``` javascript
传入：str: string
传出： string 
```

##### 3.举例

```ts
const a = Tsrv.utils.DeCode('WYFhYWE=');
//'aaaaa'
```

#### getGUID

##### 1.功能说明

```sh
delimiter 是否要分隔符 默认true
```

##### 2.参数说明

```javascript
传入：delimiter: boolean = true
传出： string 
```

##### 3.举例

```
cosnt Guid = Tsrv.utils.getGUID();
//0f2bb124-8e73-4b80-b389-b34c182b4ba4
```



#### valueToFilter

##### 1.功能说明

```ban
2.0版本过滤条件是mongo
```

##### 2.参数说明

```javascript
传入：type:string,  condition:string,   value: any
传出： any
```

##### 3.举例

```
需代入系统理解
```



#### toHump

##### 1.功能说明

```sh
横线转驼峰写法
```

##### 2.参数说明

``` javascript
传入：name: string
传出：string
```

##### 3.举例

``` ts
const aq-sw = Tsrv.utils.toHump('aqSw');
```



#### toLine

##### 1.功能说明

```sh
驼峰转横线写法
```

##### 2.参数说明

```javascript
传入：name: string
传出：string
```

##### 3.举例

```sh
const aqSw = Tsrv.utils.toHump('aq-sw');
```





#### findComponent

##### 1.功能说明

```sh
转换组件名"含'-'变成oname,不含'-'的就成o-nam
```

##### 2.参数说明

```javascript
传入：name: string
传出：string
```

##### 3.举例

```ts
const aa-a = Tsrv.utils.findComponent('oaaa');
const oaaa = Tsrv.utils.findComponent('o-aaa');
```

#### noValue

##### 1.功能说明

```sh
判断传入的值是否为 null|undefined，""|"   "，[]，{},传出boolean
```

##### 2.参数说明

```javascript
传入：val: any
传出：boolean
```

##### 3.举例

```ts
const aa|a = Tsrv.utils.noValue('    ');//true
```



#### isJSONString

##### 1.功能说明

```sh
判断传入的值是否为 string,传出boolean
主要判断是否为JSON格式字符串："{}"
```

##### 2.参数说明

```javascript
传入：str: string
传出：boolea
```

##### 3.举例

```ts
const "aaaa" = Tsrv.utils.isJSONString(true);
```

#### splitM2OField

##### 1.功能说明

```sh
切分m2o的字符串
```

##### 2.参数说明

```javascript
传入：field: string
传出：any
```

##### 3.举例

````ts
const p : string = "aa|bb|xx|ss";
console.log(Tsrv.utils.splitM2OField(p)) //{type: 'aa', field: 'bb', toTable: 'xx', toField: 'ss'}
````

#### getM2OConfig

##### 1.功能说明

```sh
传入字符串或对象类型，并根据val的类型返回不同的配置对象
```

##### 2.参数说明

```javascript
传入：val: string | object
传出：any
```

##### 3.举例

````ts
const p : string = "aa：bb：xx：ss";
console.log(Tsrv.utils.getM2OConfig(p)) //{toTable: 'dd', toField: 'ss', fields: Array(0), isDropdown: false}
````

#### splitSelectionField

##### 1.功能说明

```sh
传入值遇到 ‘|’切分成，返回type，field，selectionID
如果传入值的切分值长度小于3组，返回NUll。
```

##### 2.参数说明

```javascript
传入：field: string
传出：object
```

##### 3.举例

````ts
const p : string = "aa：bb：xx：ss";
console.log(Tsrv.utils.getM2OConfig(p)) //{toTable: 'dd', toField: 'ss', fields: Array(0), isDropdown: false}
````

#### joinTF

##### 1.功能说明

```sh
链接table和field
```

##### 2.参数说明

```javascript
传入：table: string, field: string
传出：string
```

##### 3.举例

````ts
const p : string = "aa",;
console.log(Tsrv.utils.joinTF(p)) //{aa.bb}
````

#### configRecurse

##### 1.功能说明

```sh
递归权限 需代入浏览器vue插件理解
```

##### 2.参数说明

```javascript
传入：config: any, data: any, property: string
传出：any
```

##### 3.举例

````ts
config为组件配置信息 需代入浏览器vue插件理解
````

#### configRecurseSingle

##### 1.功能说明

```sh
递归权限  
```

##### 2.参数说明

```javascript
传入：config: any, data: any, type: string
传出：any
```

##### 3.举例

````ts
config为组件配置信息  需代入浏览器vue插件理解
````



#### createModal

##### 1.功能说明

```sh
用于创建一个弹窗（模态框）并返回一个Promise对象
```

##### 2.参数说明

```javascript
传入：name: string, config: any
传出：any
```

##### 3.举例

````ts
需要代入系统理解
````

#### isContainChinese

##### 1.功能说明

```sh
判断是否包含中文
```

##### 2.参数说明

```javascript
传入：str
传出：any
```

##### 3.举例

````ts
console.log(Tsrv.utils.isContainChinese('小单'))//true
````

#### getFileExt

##### 1.功能说明

```sh
获取文件扩展名
```

##### 2.参数说明

```javascript
传入：fileSrc: string
传出：string
```

##### 3.举例

````ts
const p : string = "a.ts",;
console.log(Tsrv.utils.getFileExt(p)) //{ts}
````

#### getFileName

##### 1.功能说明

```sh
获取文件名包含扩展名
```

##### 2.参数说明

```javascript
传入：fileSrc: string
传出：string
```

##### 3.举例

````ts
const p : string = "a.ts",;
console.log(Tsrv.utils.getFileName(p)) //{a}
````

#### getFileType

##### 1.功能说明

```sh
获取文件的类型
```

##### 2.参数说明

```javascript
传入：id: string, isThumb: boolean = true
传出：string
```

````ts
const p : string = "a.jpg",;
console.log(Tsrv.utils.getFileType(p)) //{image}
````


#### getFileSrc

##### 1.功能说明

```sh
获取文件的路径
```

##### 2.参数说明

```javascript
传入：id: string, isThumb: boolean = true
传出：string
```

````ts

````

#### dataURLtoBlob

##### 1.功能说明

```sh
将传入的dataual值转换为blob对象
```

##### 2.参数说明

```javascript
传入：dataurl: string
传出：any
```

##### 3.举例

````ts

````

#### downloadFile

##### 1.功能说明

```sh
下载文件
```

##### 2.参数说明

```javascript
传入：url: string, name: string
传出：void
```

##### 3.举例

````ts
Tsrv.utils.downloadFile(url,name)
````

#### downloadFileByBase64

##### 1.功能说明

```sh
下载文件（按Base64）
```

##### 2.参数说明

```javascript
传入：base64: string, name: string
传出：void
```

##### 3.举例

````ts
Tsrv.utils.downloadFileByBase64(
           base64
           name
          );
````

#### getColumnType

##### 1.功能说明

```sh
获取列类型
```

##### 2.参数说明

```javascript
传入：column: ColumnConfig
传出：any
```

##### 3.举例

````ts
const column = {
  editRender: {
    name: 'oNumberInput'
  }
};
const p = getColumnType(column);
console.log(Tsrv.utils.getColumnType(p));//{name: 'oNumberInput',type: 'number',renderType: 'number'}
````

#### getURLParam

##### 1.功能说明

```sh
获取url参数值
```

##### 2.参数说明

```javascript
传入：name: string
传出：any
```

##### 3.举例

````ts
假设 url = https://www.example.com/?name=John&age=25&gender=male

const name = Tsrv.utils.getURLParam('name');
console.log(name); // 输出：John

const age = Tsrv.utils.getURLParam('age');
console.log(age); // 输出：25

const gender = Tsrv.utils.getURLParam('gender');
console.log(gender); // 输出：male

const address = Tsrv.utils.getURLParam('address');
console.log(address); // 输出：null
````

#### GetYearFirstWeekDays

##### 1.功能说明

```sh
获取一年第一周的天数
```

##### 2.参数说明

```javascript
传入：year: number, mode: number
传出：number
```

##### 3.举例

````ts
//当mode为6， 周日算一周起始
console.log(Tsrv.utils.GetYearFirstWeekDays(2024,6));//6
// 当mode不为6
console.log(Tsrv.utils.GetYearFirstWeekDays(2024,1));//7
````

#### GetYearLastWeekDays

##### 1.功能说明

```sh
获取一年最后一周的天数
```

##### 2.参数说明

```javascript
传入：year: number, mode: number
传出：number
```

##### 3.举例

````ts
//当mode为6， 周日算一周起始
console.log(Tsrv.utils.GetYearLastWeekDays(2023,6));//1
// 当mode不为6
console.log(Tsrv.utils.GetYearLastWeekDays(2023,1));//7
````

#### GetYearSumWeeks

##### 1.功能说明

```sh
得到一年总周数 (该函数计算2023年总周数时为51周，实际应为52周，问题待解决)
```

##### 2.参数说明

```javascript
传入：year: number, mode: number
传出：number
```

##### 3.举例

````ts
//当mode为6， 周日算一周起始
console.log(Tsrv.utils.GetYearSumWeeks(2023,6));//51
// 当mode不为6
console.log(Tsrv.utils.GetYearLastWeekDays(2023,1));//5
````

#### GetCurrWeekByDate

##### 1.功能说明

```sh
传入日期和模板,得到当年周数   (当mode为6时，输出值一直是202401，待解决)
```

##### 2.参数说明

```javascript
传入：date: any, mode: number
传出：string
```

##### 3.举例

````ts
let date = new Date('2023-12-31')
//当mode为6， 周日算一周起始
console.log(Tsrv.utils.GetCurrWeekByDate(date,6));//202401
// 当mode不为6
console.log(Tsrv.utils.GetCurrWeekByDate(date,1));//202352
````

#### addTreeKeyValue

##### 1.功能说明

```sh
在树结构数组中加入id 和 parentID。如果对象带keyName 则不处理,但callBack会执行
```

##### 2.参数说明

```javascript
传入：treeArr: Array<object>,
  callBack: any,
  keyName: string = 'id',
  childrenName: string = 'children',
  parentName: string = 'parentID'
传出：void
```

##### 3.举例

````ts
需代入系统理解
````

#### listAssign

##### 1.功能说明

```sh
将对象source的相同属性值复制到target
```

##### 2.参数说明

```javascript
传入：source: object, target: object
传出：void
```

##### 3.举例

````ts
let source : {
  [key: string]: any;
  } = {
    a:1,
    b:2
  }
  let target : {
  [key: string]: any;
  } = {
    a:'ssa',
    b:'vv',
    c:'ss'
  }
    Tsrv.utils.listAssign(source,target)
  console.log(target);//{ a: 1, b: 2, c: 'ss' }
````

#### objAttrClear

##### 1.功能说明

```sh
所有属性为null
```

##### 2.参数说明

```javascript
传入：bobj: object
传出：any
```

##### 3.举例

````ts
console.log(Tsrv.utils.objAttrClear({
    a:'aa',
    b:11
  }));//{ a: null, b: null }
````

#### getDateFromDay

##### 1.功能说明

```sh
根据传入的星期获取日期
创建一个新的Date对象，赋值给变量date。
使用P_dayDate.getTime()获取P_dayDate的时间戳，并加上P_day天数对应的毫秒数（P_day * 24 * 60 * 60 * 1000）。
使用date.setTime方法将新的时间戳设置给date对象，以更新日期。
返回更新后的date对象作为函数的结果。
```

##### 2.参数说明

```javascript
传入：P_dayDate: Date, P_day: number
传出：date
```

##### 3.举例

````ts
const dayDate = new Date('2023-07-22');
const p_day = 7;

const result = Tsrv.utils.getDateFromDay(dayDate, p_day);
console.log(result); //2023-07-29
````

#### getWeekStartByDate

##### 1.功能说明

```sh
根据给定日期获取一周的起始日期
```

##### 2.参数说明

```javascript
传入：P_date:Date , P_mode:number 
传出：Date
```

##### 3.举例

````ts
let date = new Date('2023-12-31')

console.log(Tsrv.utilsgetWeekStartByDate(date,7))//2023-12-25T00:00:00.000Z
````

#### GetCurrWeekByDateNew

##### 1.功能说明


```sh
GetCurrWeekByDatede的更新版，根据给定日期获取一周的起始日期的更新版
```

##### 2.参数说明

```javascript
传入：P_date:Date , P_mode:number 
传出：Object
```

##### 3.举例

````ts

````

#### downl

##### 1.功能说明

```sh
下载文件（按Base64）
```

##### 2.参数说明

```javascript
传入：base64: string, name: string
传出：void
```

##### 3.举例

````ts

````

#### downl

##### 1.功能说明

```sh
下载文件（按Base64）
```

##### 2.参数说明

```javascript
传入：base64: string, name: string
传出：void
```

##### 3.举例

````ts

````

#### downl

##### 1.功能说明

```sh
下载文件（按Base64）
```

##### 2.参数说明

```javascript
传入：base64: string, name: string
传出：void
```

##### 3.举例

````ts

````

#### downl



