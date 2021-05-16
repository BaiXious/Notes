## Day515
1. 变量要经过声明和赋值后再使用
2. 变量数据类型 
    * 基本数据类型：
         - 整型：byte \ short \ int \long
         - 浮点型： float \ double
         - 字符型： char
         - 布尔型： boolean
    * 引用数据类型：
         - 类（class）: 注意String就属于该类型
         - 接口（interface）
         - 数组（array）
3. 变量类型转换
      * 自动类型提升：
         结论：当容量小的数据类型的变量与容量大的数据类型的变量做运算时，结果自动提升为容量大的数据类型。
	      byte 、char 、short --> int --> long --> float --> double 
	      特别的：当byte、char、short三种类型的变量做运算时，结果为int型
      * 强制类型转换：
         加（），注意会有精度损失
