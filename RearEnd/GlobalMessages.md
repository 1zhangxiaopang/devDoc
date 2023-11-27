
### 提示消息

````sh

	//服务器繁忙
	ErrorReasonServerBusy = "100,BE,0,Server is busy"
	//验证失败
	ErrValidationFailed = "101,BE,11,verification failed"
	//请重新登陆
	ErrorReasonReLogin = "103,BE,0,Token has expired, please login again"
	//页面不存在
	NoPageMsg = "104,BE,11,page not exists"
	//密码长度不符合规则
	ErrPwdLen = "105,BE,11,Password length does not conform to the rule"
	//密码错误
	ErrPwd = "106,BE,11,Incorrect password"
	//并发用户数超出允许范围
	CurrUserNumOverflow = "107,BE,11,More concurrent users than allowed"
	//系统需要授权
	SystemAuth = "108,BE,11,System requires authorization"
	//旧密码不正确
	OldPwdErr = "109,BE,11,The old password is incorrect"
	//密码不符合复杂性要求
	PWDComplexity = "110,BE,11,Password complexity requirements"
	//用户已禁用
	UserDisabled = "111,BE,11,User disabled"
	//管理员不能禁用
	AdminDenyDisabled = "112,BE,11,Administrator account cannot be disabled"
	//管理员贴不能删除
	DenyDelAdmin = "113,BE,11,Administrator account cannot be deleted"
	// 此规则不存在或未被批准
	NotApprovedOrDoesNotExist = "114,BE,11,This rule does not exist or is not approved"
	// 未编译的规则不能审核
	UncompiledRules = "115,BE,11,Uncompiled rules cannot be approved"
	// 此规则已在规则引擎池中，请先操作[退出运行库]后再反审核!
	// 此规则已在规则引擎池中，请先操作[退出运行库]后再编译!
	RuleIsAlreadyInPool = "116,BE,11,This rule is already in the rule engine pool"
	// 图内容空
	FlowchartIsEmpty = "117,BE,11,Flowchart is empty"
	//值不合法[{0}]
	ValueMismatch = "118,BE,11,Value mismatch"

	//操作成功
	Success = "200,BE,0,Successful operation"
	//数据由系统自动维护，不可删除
	DenyDelete = "201,BE,11, Deny delete"
	//数据由系统自动维护，不可修改
	DenyUpdate = "202,BE,11, Deny update"
	//数据由系统自动维护，不可新增
	DenyInsert = "203,BE,11, Deny insert"
	//只有管理员才能更改密码
	DenyChgPwd = "204,BE,11, Only the administrator can change the password"
	//无权限
	NoPms = "205,BE,11,No permission"
	//权限模块不包括这个功能[xxx]|
	PmsNotInFunc = "206,BE,11,The permission module does not include this function"
	//非管理员不能修改他人帐户信息
	NonAdminAct_chg_acctInfo = "207,BE,11,Non administrator cannot modify other person account information"
	//没有新的内容
	NothingNew = "208,BE,11,nothing new"
	//没有数据被更新
	NoUpdateRow = "209,BE,11,No data has been updated"
	//没有数据被删除
	NoDeleteRow = "210,BE,11,No data was deleted"
	//没有新增数据
	NoInsertRow = "211,BE,11,No new data"
	//内部API
	InternalUerOnly = "212,BE,11,This API is for internal use only"
````

### 错误消息

````sh
//未定义的类型
	UndefinedType = "-106,BE,80,Undefined type"
	//传参为空
	ParameterIsEmpty = "-107,BE,80,The parameter is empty"
	//不能识别的元素
	Unrecognizedlement = "-111,BE,80,Unrecognized element"
	//数据空
	DataIsEmpty = "-119,BE,80,Data is empty"
	//用户名或密码错误
	DBLoginAuthErr = "-500,BE,50,wrong user name or password"
	//类型转换失败
	DBTypeConversionFailed = "-501,BE,80,Type conversion failed"
	//字符串为空
	ErrStringIsNull = "-502,BE,50,String is empty"
	//无效的Token
	ErrInvalidToken = "-506,BE,50,Invalid token"
	//无效的参数
	ErrInvalidParams = "-507,BE,50,Invalid parameter"
	//生成json错误
	ErrCreateJSON = "-508,BE,80,JSON generation error"
	//令牌与用户不匹配
	ErrTokenOrID = "-509,BE,90,Token does not match user"
	//json格式不正确
	NotValidJSON = "-510,BE,80,Not a valid json format file"
	//缺少i18n属性
	NotI18nAttr = "-511,BE,80,json file has no 'i18n' element"
	//不能识别的命令
	Unrecognizedcommands = "-512,BE,90,Unrecognized commands"
	//数据库事务已打开
	TransactionOpened = "-513,BE,80,Database transaction opened"
	//未开启事务
	TransactionNotOpened = "-514,BE,50,Transaction not opened"
	//无法识别的字段数据类型
	UnrecognizedFieldDataType = "-515,BE,80,Unrecognized field data type"
	//字段表达式错误
	FieldExpressionError = "-516,BE,80,Field expression error"
	//请求失败
	RequestFailed = "-517,BE,80,Request failed"
	//文件内容为空
	FileContentIsEmpty = "-518,BE,80,File content is empty"
	//列数超出100
	ColumnsExceeded = "-519,BE,80,The number of columns exceeds the limit"
	//字段类型不能识别
	FieldTypeErr = "-520,BE,80,The field type is not recognized"
	//表字段不能改为子查询字段
	ErrChangeSubqueryField = "-521,BE,80,Table fields cannot be changed to subquery fields"
	//存储过程返回不合法的json
	SPReturnInvalidJSON = "-522,BE,80,The stored procedure returns invalid JSON"
	//空编号
	EmptyNumber = "-523,BE,80,Empty number"
	//编号超过指定长度
	SuperLong = "-524,BE,80,Number exceeds set length"
	//无法识别的文件类型
	UnrecognizedFileType = "-525,BE,80,Unrecognized file type"
	//不接受的文件类型
	FileTypeDeny = "-526,BE,80,File type not accepted"
	//文件不存在
	FileNotExist = "-527,BE,80,File does not exist"
	//文件名格式不合法
	InvalidFileName = "-528,BE,80,File name format is invalid"
	//不合法的JSON串
	InvalidJSON = "-529,BE,80,JSON string is invalid"
	//json表达式不是一个数组
	JSONNotArray = "-530,BE,80,JSON expression is not an array"
	//权限角色不存在
	PMSRoleNotExist = "-531,BE,80,Permission role does not exist"
	//找不到审核流程节点
	FlowIDisNULL = "-532,BE,80,Approval process node not found"
	//子查询SQL语法缺少where条件
	SubquerySQLSyntaxError = "-533,BE,80,Subquery SQL syntax is missing the where condition"
	//同级别多个重复的角色
	RoleConflict = "-534,BE,80,Multiple duplicate roles at the same level"
	//流程图缺少开始节点
	MissingStartNode = "-535,BE,80,Flowchart missing start node"
	//没有要审批的对象
	NoUsersToApprove = "-536,BE,80,There are no objects to approve"
	//重复提交送批
	RepeatedSubmission = "-537,BE,80,Repeated submission for approval"
	//清单中含有不合法的帐单
	ContainsIllegalBills = "-538,BE,80,The list contains illegal bills"
	//正在送批中
	SendingApproval = "-539,BE,80,Sending approval"
	//制单人为空
	BillerIsEmpty = "-540,BE,80,Biller is empty"
	//需要走呈批流程
	NeedApproval = "-541,BE,80,Need to go through the approval process"
	//由管理模块接管
	TakenOverByBM = "-542,BE,80,Taken over by management module"
	//非法IP地址
	IllegalIPaddress = "-543,BE,80,Illegal IP address"
	//非法端口号
	IllegalHostPort = "-544,BE,80,Illegal host port"
	//用户不存在
	UserNotExist = "-545,BE,80,user does not exist"
	//工作ID超出数量
	WorkerIDExcess = "-546,BE,90,Worker ID excess of quantity"
	//MTO没有指定描述字段
	DescFieldIsEmpty = "-547,BE,80,Description field is empty"
	//无法序列化 bson
	SerializeBSONFailed = "-548,BE,80,Failed to serialize BSON"
	//无法序列化 json
	SerializeJSONFailed = "-549,BE,80,Failed to serialize JSON"
	//系统数据库资料缺失
	SysDBDataMissing = "-550,BE,99,Missing data in system database"
	//未知的错误
	UnknownError = "-551,BE,99,unknown error"
	//系统保留字[{0}]
	ContainsKeyword = "-552,BE,80,The new field name contains  keyword"
	//存在无效字符
	InvalidCharacter = "-553,BE,80,Invalid character exists"
	//不是期望的类型
	NotTheExpectedType = "-554,BE,90,Not the expected type"
	//超时
	TimeOut = "-555,BE,90,Time out"
	//服务注册失败
	SvcRegFailure = "-556,BE,90,Service registration failure"
	//配置文件内容错误
	ConfFileContentErr = "-557,BE,90,Configuration file content error"
	//获取数据失败
	GetDataFailed = "-558,BE,90,Failed to get data"
	//处理数据失败
	ProcessDataFailed = "-559,BE,90,Failed to process data"
	// 无法打开文件
	OpenFileFailed = "-560,BE,90,Failed to open  file"
	// 读失败
	ReadFailed = "-561,BE,90,Read failed"
	// 写失败
	WriteFailed = "-562,BE,90,Write failed"
	// copy失败
	CopyFailed = "-563,BE,90,Copy failed"
	// 提交失败
	CommitFailed = "-564,BE,90,Commit failed"
	// 不匹配
	NotMatch = "-565,BE,90,Not match"
	// 删除失败
	RemoveFailed = "-566,BE,90,Remove failed"
	// 新建目录失败
	MakeDirFailed = "-567,BE,90,Make Dir failed"

	//主功能名空
	MainFunNameIsNull = "-1001,BE,90,Main function not specified"
	//外键约束
	ForeignKeyConstraint = "-1002,BE,80,Foreign key constraint"
````


