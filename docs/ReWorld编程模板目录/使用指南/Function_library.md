> 函数库:  

> [!note|label:函数以及参数]
```lua

--[[已存在系统函数:
FunTable.InitTable.Event()  -- 初始化事件对象
FunTable.InitTable.Folder() -- 通用存储层级文件初始化
FunTable.InitTable.Value() -- 数值初始化

-- 商城数据表
FunTable.SysCallTable.ShopTable = {
	-- 工作区商品模型文件夹名称
	shop = "" ,
	--商品表
	-- price : 商品价格 ; name : 商品名(不可重复!!!) ; id : 商品模型的资源ID ; [1] : 索引
	product_table = {
		[1] = {price = 10 , name = "A" , id = "rwid://T78iPKuulAti9xkijX"},
		[2] = {price = 20 , name = "B" , id = "rwid://T7k.PK4RDGti9okijX"},
		[3] = {price = 30 , name = "C" , id = "rwid://T78iPKFdpGti9okijX"}
	},
	--商店UI的ID表
	-- leftButtonId : 上一件商品按钮的ID ; rightButtonId : 下一件商品按钮的ID ; shopButtonId : 打开商店的图标ID 
	-- buyButtonId : 购买商品的图标ID ; closeButtonId : 关闭商店的图标ID ; monneyImageId : 金币的图标ID 
	-- monneyInsufficientId : 金额不足提示图标ID ; buySuccessId : 购买成功提示图标ID ; ownedshop : 提示已经拥有的图标ID
	shopuitable_id={
		leftButtonId="rwid://T7kKPKA0hR0.9okijN",
		rightButtonId="rwid://T7kKPKA0hR0.9okijN",
		shopButtonId="rwid://T7kKPKA0hR0.9okijN",
		buyButtonId="rwid://T7k.PKVMkR0.9okijN",
		closeButtonId="rwid://T7xdPKZFiR0.9okijN",
		monneyImageId= "rwid://T7k.PKldUx0d9okijN",
		monneyInsufficientId= "rwid://T7k.PKldUx0d9okijN",
		buySuccessId= "rwid://T7k.PKldUx0d9okijN",
		ownedshop = "rwid://T7k.PKldUx0d9okijN"
	}
}

-- 更新金额函数 <number_value : 存入金额数 ; playerid : 玩家ID , 提供数据存储空间 : MONNEYDATASTORE , 注: 该存储空间用于存储玩家拥有的金额数,可外部获取>
FunTable.SysCallTable.UpdateMonney(number_value,playerid)

-- 商城初始化 <player : 玩家对象 ; S_C : 只能为"Server"或者"Client"(Text类型) , 服务器端用"Server" , 客户端用"Client">
-- 注: 该函数系统需要使用者自主提供相应的商城展示模型(MeshPart类型),并在WorkSpace下面创建一个组合单位,命名为: Shop
FunTable.InitTable.Shop(player , S_C) 

-- 新手引导初始化 <image_num 引导图片数量 ;imageid_table 引导图片ID表(类型:table) ;leftbutton_id 左边按钮图片ID ;rightbutton_id 右边按钮图片ID ;playerknowbutton_id 我知道了按钮ID>
FunTable.InitTable.Guide(image_num ,imageid_table ,leftbutton_id ,rightbutton_id ,playerknowbutton_id)

-- 角色数据初始化 <该函数需要传入参数:avatar(角色实体)>
FunTable.InitTable.Avatar(avatar)

-- UI界面数据初始化 <该函数需要传入参数:Uid(玩家的ID) ;介绍:该函数会创建一个2D父级容器(GamePrepareUI) ;相关数据修改须在"数值初始化"中完成>
FunTable.InitTable.UI(Uid) 

-- 摄像机数据初始化 <相关数据修改须在"数值初始化"中完成>
FunTable.InitTable.Camera() 

-- 环境数据初始化 <相关数据修改须在"数值初始化"中完成>
FunTable.InitTable.Environment() 

--——————————CommonStorage——————————--
-- interval_time 调用函数的等待时间(浮点型) ;loop_time 计时器执行次数(整型) ;close_ui 关闭对象界面
FunTable.SysCallTable.WaitClose(interval_time,loop_time,close_ui) -- 延时关闭函数

-- type_name 需要检查的类型名 ;sys_model 需要检测的组合
FunTable.SysCheckChildType(type_name,sys_model) -- 检查组合单位下特定的子集类型函数
--——————————CommonStorage——————————--

--——————————Server——————————--
-- interval_time 调用函数的等待时间(浮点型) ;loop_time 计时器执行次数(整型) ;bool_value 是否停止计时
FunTable.SysCallTable.ComputationTime(bool_value,interval_time,loop_time) -- 计时函数

-- avatar 扣血对象 ;material_type 材质类型 ;materrail_name 材质名称 ;damage_value 每次扣血量
FunTable.SysCallTable.CountinueDamage(avatar,material_type,materrail_name,damage_value) -- 持续扣血函数
--——————————Server——————————--

--——————————Client——————————--
-- 注:客户端函数需要在玩家实体加载后调用
-- image_num 引导图片数量 ;imageid_table 引导图片ID表(类型:table) ;leftbutton_id 左边按钮图片ID ;rightbutton_id 右边按钮图片ID ;playerknowbutton_id 我知道了按钮ID
FunTable.SysCallTable.BeginnerGuidance(image_num ,imageid_table ,leftbutton_id ,rightbutton_id ,playerknowbutton_id) -- 新手引导函数
--——————————Client——————————--
]]--

```