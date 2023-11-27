
### o-combobox(下拉列表框)

名字：

* 说明

  本组件旨在替换原1.0版本中众多输入选择窗口，例如：o-i18n-select o-icon-select 。

#### 功能说明

* 本组件来自于i-view \<Select\>选择器
* 多个o-combobox实现联查功能
* 输入动态筛选

* 内容国际化
* config 如果不传任何信息，内部会定义初始数据;
* compBoxInfo子组件不传则内部会自动新建组件内部compBoxInfo

#### prop

* compBoxInfo   子组件组件对象

* value v-mod双向绑定 

  

* config  配置信息


  | 参数             | 说明                                | 类型    | 可选值                        | 默认值                                               |
  | ---------------- | ----------------------------------- | ------- | ----------------------------- | ---------------------------------------------------- |
  | size             |                                     | string  | large、small、default或者不填 | 'default'                                            |
  | multiple         | 多选时返回数组，单选时返回对象      | boolean |                               | false                                                |
  | disabled         | 可用状态                            | boolean |                               | false                                                |
  | placeholder      | 选择框默认文字 i18n value           | string  |                               | ' '                                                  |
  | i18n             |                                     | obj     |                               |                                                      |
  | ├─ field         | 属性字段是否国际化转换              | boolean |                               | false                                                |
  | ├─ list          | 数据list是否国际化转换              | boolean |                               | false                                                |
  | filter           | 过滤（启用过滤会降低性能）          | obj     |                               | '{$and:{name:'xxx',name1:8,$or:[{name:1},{name1:2}]}}' |
  | field            | 列表字段（注意与数据对应顺序）      | array   |                               | [' ',' ']                                            |
  | keyField         | 一行的key值字段                     | string  |                               | ' '                                                  |
  | displayField     | 选择后显示的字段                    | string  |                               | ' '                                                  |
  | list             | 数据列表                            | array   |                               |                                                      |
  | ├─ type          | iconFont 图字符列表 / text 文字列表 | string  |                               | 'text/iconFont'                                      |
  | ├─ data          |                                     | obj     |                               |                                                      |
  | │  ├─ fieleName  | fieldName = field内的字段名         | string  |                               | ' '                                                  |
  | │  └─ fieldName1 | fieldName = field内的字段名         | string  |                               | ' '                                                  |
  

* 示例

  ````json
  {
      size?:'default', //可选值为large、small、default或者不填
      multiple?:false, //多选时返回数组，单选时返回对象
      disabled?:false, //可用状态 
      
      placeholder:'',//选择框默认文字 i18n value
      i18n?:{                 
           field:false, //属性字段是否国际化转换
           list:false   //数据list是否国际化转换
       },
      
      //过滤
      filter?:{$and:{name:'xxx',name1:8,$or:[{name:1},{name1:2}]}}, //启用过滤会降低性能
     
      //列表字段
      field:['',''],  //注意与数据对应顺序
      keyField:'',	//一行的key值字段
      displayField:'', //选择后显示的字段
      //数据列表
          list:[
              {
                  type:'text|iconFont',  // iconFont 图字符列表 | text 文字列表
                
                  data:	 
                          {
                             fieldName:'', //fieldName = field内的字段名
                             fieldName1:'', //fieldName = field内的字段名
                              ...
                          }   
                       
              }
          ] 
   
  }
  ````

#### 事件

* on-change 选择改变时 

  返回数据：

  ````json
  单选时一条数据，多选时多条数据
  [
      {
           key:"xxx",    选择的值
      	 row:{        //prop config.list[]数据
     		 		type:"xxx",
     		 		data:{}
           }
      }
     
  ]
  ````

  

* on-select 选择时

  ````sh 
  ````
  
  

#### 方法

initValue(v:string|Array<any>) 初始化combobox值 通过compBox调用

### oCardBox 卡片箱

#### 功能说明

#### prop

#### 事件

#### 方法

### oOpenGraphData  打开g6画布

#### 功能说明 

#### prop

#### 事件

#### 方法

### oSimpleTable  简易表格

#### 功能说明 

#### prop

#### 事件

#### 方法

### oSimpleToolbar  简易工具栏

#### 功能说明 

#### prop

#### 事件

#### 方法

### oFlowchart  流程图编辑器

#### 功能说明 

#### prop

#### 事件

#### 方法

### o-dialog-box

## 架构说明

## 代码模板

* 说明

  ````````json
  ????
  ````````

  

### vue

  vscode -> 文件->首选项->配置用户代码片断->vue.json

```json
{
	// Place your snippets for vue here. Each snippet is defined under a snippet name and has a prefix, body and 
	// description. The prefix is what is used to trigger the snippet and the body will be expanded and inserted. Possible variables are:
	// $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. Placeholders with the 
	// same ids are connected.
	// Example:
	"Print to console": {
		"prefix": "vue",
		"body": [
			"<!--",
			"******功能应用组件模板******",
			"功能应用组件:是最终应用程序的根组件,它注册在系统功能里。例如：权限设置，开发模块，逻辑引擎等",
			"引用注册在全局Tsrv.compBox里, 参数需要compID+name+funName写全。",
			"参考开发模块devModal写法",
			"-->",
			"<template>",
			"<div class=\"init-container\"></div>",
			"<!-- 一个组件要调用多个相同组件时,传入compBoxInfo对象，让子组件注册在一个组件箱内-->",
			"<!--例：<xxx :compBoxInfo=\"GT_compBoxInfo\" -->",
			"<!-- 一个组件要调用多个相同组件时,组件箱内引用实例冲突。不需传入compBoxInfo由组件内部产生实例，只需接收compBoxInfo对象-->",
			"<!--例：<xxx  @compBoxInfo=\"set???CompBoxInfo\"-->",
			"</template>",
			"",
			"<script lang=\"ts\">",
			"import { Tsrv, T_srv, ifs, ts, vue, I_cmd, Tcmd } from './config';",
			"",
			"@T_srv.comp",
			"export default class ??? extends vue {",
				"/*父组件compBoxInfo*/",
				"@T_srv.prop({",
					"required: false,",
					"type: Object,",
					"default: null",
					"})",
					"compBoxInfo: ifs.I_compBoxInfo;",
					"",
			"/*组件名*/",
				"private G_compName : string = '???'",
				"/* 组件箱信息对象 */",
				"private GT_compBoxInfo: ifs.I_compBoxInfo;",
			"",
				"/* 组件箱对象 */",
				"private GT_compBox: ifs.I_compBox;",
			"",
				"/* 组件箱识别ID */",
				"private G_compID: string;",
				 "/* 指挥部 */",
  "private GT_command: I_cmd = Tcmd;",
								"",
				"/* 一个组件要调用多个相同组件时,组件箱内引用实例冲突,在此要定义实例变量接收,并在方法里加get 和 set  */",
				"// private GT_???CompBoxInfo : ifs.I_compBoxInfo;",
				"// private GT_???CompBoxInfo : ifs.I_compBoxInfo;",
				"// public get???CompBoxInfo(): ifs.I_compBoxInfo{",
					"//   return this.GT_compBoxInfo",
				"// }",
				"",
				"// public set???CompBoxInfo(e :ifs.I_compBoxInfo):void{",
					"//   this.GT_compBoxInfo = e",
				"// }",
				"",
				"created() {",
				"//如果父组件没有传参，那就产生一个",
				  "this.GT_compBoxInfo = Tsrv.getCompInfo(this.compBoxInfo);",
					 "this.G_compID = this.GT_compBoxInfo.compID;",
					 " this.GT_compBox = this.GT_compBoxInfo.TcompBox;",
					 "this.GT_command.init(this, this.GT_compBoxInfo);",
					 "}",
							"mounted() {",
							"",
							"",
					"/* 向父组件发送实例 */",
					"this.GT_compBox.addCompMergeName(this.G_compID, this.G_compName, this);",
					"this.'$'emit('compBoxInfo',this.GT_compBoxInfo);",
					"",
					"/* 最终应用组件向外抛出引用实例,以供应用间调用 */",
					"// Tsrv.compBox.addCompMergeName(",
					"//   Tsrv.compBox.getDefGUID(), // 全局compBox",
					"//   '????',",
					"//   this,",
					"//   '???'",
					"// );",
					"}",
					"",
					"destroyed() {",
						"/*注册组件销毁*/",
						"this.GT_compBox.removeCompMergeName(this.G_compID, this.G_compName);",
						"",
						"/* 最终应用组件销毁*/",
					"/* this.GT_compBox.removeCompMergeName(this.G_compID, this.G_compName,'funName'); */",
					"",
					"/* 如果父组件传入的compBoxInfo则删除本文件产生的引用,反之是本组件产生的ID统一删除*/",
					"if (Tsrv.utils.isEmpty(this.compBoxInfo)) {",
						"this.GT_compBox.removeCompsWithCompID(this.G_compID);",
						"} else {",
							"this.GT_compBox.removeCompsMergeName(this.G_compID, [`'${this.G_compName}'`]);",
							"}",
							"/*如果是动态组件可能会关闭全局compBox*/",
							"// this.GT_compBox = null",
							"}",
							"}",
							"</script>",
							"<style lang=\"scss\" scoped></style>",
							"",
		],
		"description": "A vue file template"
	}
}
```

### command

````json
{
	// Place your 全局 snippets here. Each snippet is defined under a snippet name and has a scope, prefix, body and 
	// description. Add comma separated ids of the languages where the snippet is applicable in the scope field. If scope 
	// is left empty or omitted, the snippet gets applied to all languages. The prefix is what is 
	// used to trigger the snippet and the body will be expanded and inserted. Possible variables are: 
	// $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. 
	// Placeholders with the same ids are connected.

	"Print to console": {
		"scope": "javascript,typescript",
		"prefix": "Tcommand",
		"body": [
			"import { ifs } from '@/services';",
"",
"class T_cmd {",
	"  // 主组件箱",
	" private compBox: ifs.I_compBox;",
	"",
	" // 主组件ID",
	" private compID: string;",
	"",
	" // 主组件实例",
	" private self: any;",
	"",
	" // 主组件created里初始化",
  "public init(self: any, compBoxInfo: ifs.I_compBoxInfo) {",
		"  this.self = self;",
		"   this.compBox = compBoxInfo.TcompBox;",
		"  this.compID = compBoxInfo.compID;",
		"}",
		"}",
		"export interface I_cmd extends T_cmd {}",
		"export const Tcmd = new T_cmd();"
		],
		"description": "一个vue组件指挥类"
	}
}
````

### config.ts

````json
{
	// Place your 全局 snippets here. Each snippet is defined under a snippet name and has a scope, prefix, body and 
	// description. Add comma separated ids of the languages where the snippet is applicable in the scope field. If scope 
	// is left empty or omitted, the snippet gets applied to all languages. The prefix is what is 
	// used to trigger the snippet and the body will be expanded and inserted. Possible variables are: 
	// $1, $2 for tab stops, $0 for the final cursor position, and ${1:label}, ${2:another} for placeholders. 
	// Placeholders with the same ids are connected.
	"Print to console": {
		"scope": "javascript,typescript",
		"prefix": "Tconfig",
		"body": [
			"import { T_srv, Tsrv, ifs, ts, tvs, vue } from '@/services';",
"import { I_cmd, Tcmd } from './command';",
"",
"export { I_cmd, T_srv, Tcmd, Tsrv, ifs, ts, tvs, vue };",
		],
		"description": "Log output to console"
	}
}
````

### types.ts

```sh

import { ifs } from '@/services';
import Vue from 'vue';

export namespace N_oBasePanel {
  export interface oBasePanel extends Vue {
    useTable: boolean;

    config: any;

    needSave: boolean;

    randomTabName: string;

    loading: boolean;

    isExpand: boolean;

    isOpenPrint: boolean;

    selectedPrintTemp: string;

    isPanelSingle: boolean;

    name: {
      formName: string | null;
      tableNames: string[];
    };

    funName: {
      formName: string | null;
      tableNames: string[];
    };

    forms: Array<any>;

    tables: Array<any>;

    tablesLength: number;

    toolbar: any;

    hasRequestAudit: boolean;

    tagsControl: any;

    formID: any;

    isLoadEditLock: boolean;

    searchControl: {
      split: number;
      isSearchOpen: boolean;
      isSearchBoxOpen: boolean;
      isSearchFullOpen: boolean;
      pageNo: number;
      total: number;
      tagsControl: {
        audit: false;
      };
      name: {
        formName: string | null;
        tableNames: string[];
      };
      funName: {
        formName: string | null;
        tableNames: string[];
      };
      G_compName: string;
      GT_compBoxInfo: ifs.I_compBoxInfo;
      GT_compBox: ifs.I_compBox;
      G_compID: string;
      formData: object; // 表头的数据
      currentTableIndex: string;
    };

    handleListener: (msg: any) => void;
    requestFilter:(cfg: any)=>void;
    handleRequstFilter(cfg: any);
    // 监听搜索结果表事件
    handleSearchResultChange(data: any);
    // 选择了简易搜索的条件
    selectSimpleSearchField(table: string, field: string, val: boolean);
    // 重置高级搜索的条件
    resetSearchForm();
    setActions(config: any);
    closeSearch();
    openSearch();
    openSearchBox();
    commitEvent(event, params?: any);
    requestAudit();
    requestSendAudit(params);
    requestSendSelect(data, params);
    auditStatus();
    selbillClick(index: number);
    queryLinkClick(index: number, row?: any);
    handleAttachClicked();
    openUploadFile(value: any);
    auditCheck(value: boolean);
    updAuditState(s: 'audit' | 'unAudit');
    delete();
    dialogDel();
    switchEdit(value: boolean);
    doPrint();
    loadData();
    print();
    receiveBaseFormDataPkg(e);
    receiveBaseGridDataPkg(e);
    setTabelM2o(data: any);
    loadTableData();
    doSearchResHandle();
    doNotSearchResHandle(res: ifs.I_queryResData<any>): Promise<Object>;
    loadFormData:(pageNo?: number, filter?: ifs.I_fv[])=> Promise<Object>;
    updateAuditStatus(row: any);
    getRecordIndexById(id: string);
    insert();
    validate();
    doActions(action: string, params: any);
    save();
    doSave(): Promise<boolean>;
    beforeDelete();
    doDelete();
    updateSaveBtnStatus();
    getBeforeSaveData();
    getAfterSaveData();
    getBeforeDeleteData();
    getAfterDeleteData();
    doCustomBtnAction(title: string, action: string, params?: any);
    prev();
    next();
    jumpTo(to: number);
    end();
    start();
  }
}

```






### setFun

### 增加配置组件

````sh
1、command.ts 增加 新组件配置 SetupInit.component.list= getComponentList();
2、attrDetail.vue releaseFromConfig()
3、attrLibField.vue releaseFromConfig()
4、 index.vue transformConfigToJson()
4. index.vue configToLibfield()   放在 965之前
5. index.vue configToLibfieldUnit()
6. index.vue configToPermission()
7. command.ts getPermissionList() 
````

### BaseGrid手动用法

````sh
  <o-base-grid
          ref="gridRole"
          :config="gridRoleConf"
          :regCustEventName="custPmsFunEventName" //定制事件 不通过标准功能名来接收事件
        />
````
