---
title: notion函数详解
date: '2022-06-23 20:53'
categories:
  - "\U0001F680技能"
  - notion
tags:
  - notion
banner_img: 'https://hexoblogzeefan.oss-cn-guangzhou.aliyuncs.com/img/202206200917436.jpg'
---


[notion多条件formula - CSDN](https://www.csdn.net/tags/NtzaggysMDE2OTctYmxvZwO0O0OO0O0O.html)


# 1 一、属性（列名-properties）

1.  prop(“属性”) 返回每个条目的“属性值”，点击即可用对应的格式插入到公式中。
    
2.  公式中的四种方式
    
    四 种 格 式 { 数 字 日 期 字 符 串 复 选 框 四种格式\begin{cases} 数字 & \\ 日期 & \\字符串 &\\复选框 & \end{cases} 四种格式⎩⎪⎪⎪⎨⎪⎪⎪⎧​数字日期字符串复选框​​
    
floor((prop("小时") + prop("分钟") / 60) * 100) / 100

# 2 二、常量（constants）

常 量 { e 自 然 对 数 的 底 数 p i 圆 周 率 t r u e 真 f l a s e 假 常量\begin{cases} e &自然对数的底数 \\ pi &圆周率 \\true &真\\flase &假 \end{cases} 常量⎩⎪⎪⎪⎨⎪⎪⎪⎧​epitrueflase​自然对数的底数圆周率真假​

# 3 三、基本运算

1.  if语法（“`if`”）：进行条件判断，在两个选项（要为同一格式）中选择一个。
    
    语法：
    
    -   `boolean?value:value`
    -   `if(boolean,value,value)`
    
    补充：在"boolean"不能填写0或者1；value中，true（真）为1，false（假）为0；
    
2.  加法（"`+`“或"`add`"）：把两个数字或字符串相加，并返回它们的值
    
    语法：
    
    -   `value+value`
    -   `add(value,value)`
    
    说明：value可以是数字或字符串，为字符串时要加上双引号
    
3.  减法（”`-`“或“`subtract`”）：将两个数字相减，并返回它们的值
    
    语法：
    
    -   `number-number`
    -   `subtract(number,number)`
4.  乘法（”`*`“或“`multiply`”）：将两个数字相乘，并返回它们的值
    
    语法：
    
    -   `number*number`
    -   `multiply(number,number)`
5.  除法（”`/` “或"`divide`"）：将两个数字相乘，并返回他们的值
    
    语法：
    
    -   `number/number`
    -   `divide(number,number)`
6.  绝对值（"`abs`"）：返回数的绝对值
    
    语法：`abs(number)`
    
7.  求余运算（”`%`“或"`mod`"）：把两个数进行求余运算，并返回它们的值
    
    语法：
    
    -   `number%number`
    -   `mod(number,number)`
8.  ”四舍五入“（”`round`“）：对数字进行”四舍五入“
    
    语法：`round(number)`
    
    说明：默认情况下只保留整数。要保留n位小数时，应使用
    
    r o u n d ( n u m b e r ∗ 1 0 n ) / 1 0 n round(number*10^n)/10^n round(number∗10n)/10n
    
9.  一元负数（”`unaryminus`“或“`-`”）：对一个数进行取它的负数
    
    语法：
    
    `-number`
    
    `unaryminus(number)`
    
    如：-3==unaryminus(3)
    
10.  一元加号（“`+`”或“`unaryPlus`”）：将参数转化为数字。
    
    语法：
    
    `+value`
    
    `unaryPlus(value)`
    
    补充：可以将true转化为1，false转化为0
    

# 4 四、关系逻辑判断

1.  关系判断
    -   大于 >
    -   小于 <
    -   等于 ==
    -   大于等于 >=
    -   小于等于 <=
    -   不等于 !=
2.  逻辑判断
    -   逻辑“`非`”：对逻辑参数进行否定
        
        语法：
        
        `not boolean`
        
        `not (boolean)`
        
    -   逻辑“`与`”：对逻辑参数进行“与”运算，`“一假全假”`
        
        语法：
        
        `boolean and boolean`
        
        `and(boolean,boolean)`
        
    -   逻辑“或”：对逻辑参数进行“或”运算，`“一真全真”`
        
        语法：
        
        `boolean or boolean`
        
        `or(boolean,boolean)`
        

# 5 五、字符串函数

1.  连接函数（“`concat`”）：将字符串进行连接
    
    语法：
    
    `concat(text...)`
    
    `text+text+...`
    
2.  插符函数（“`join`”）：插入字符函数，在其余叁数之间插入第一个参数并返回它们的连接字符串
    
    语法：`join(text...)`
    
    例如：join("-",“a”,“b”,“c”)==“a-b-c”
    
3.  切片函数（”`slice`“）：从字符串中提取子字符串（包括开头索引，不包括结尾索引[start,end)）
    
    语法：
    
    -   `slice(text,number)`
    -   `slice(text,number1,number2)`
    
    说明:只有一个数字时，就是从这个索引数字开始到结束；当有两个数字时（第二个数要大于第一个数，不然不会显示），从字符串中提取子字符串，包含开头索引，不包含结束索引。
    
    注意：字符串的索引值是从0开始的
    
4.  长度函数（”`length`“）：返回字符串的长度，返回值是一个数值。
    
    语法：`length(text)`
    
5.  转化函数（”`format`“）：将其他格式的参数转化为字符串。
    
    语法：`format(value)`
    
6.  转化函数（”`toNumber`“）：将其他格式的参数转化数字
    
    语法：`toNumber(value)`
    
    说明：
    
    -   可以把字符串类型转化为数字，如："123"到数字123
    -   可以把日期类型转化时间戳，Jan 18, 2021 7:28 PM→1610969340000
    -   可以把复选框类型转化为数字，true为1，false为0
    -   也可以把数字类型转化为数字
7.  包含判断函数（”`contains`“）：包含判断函数，返回一个boolean值，
    
    语法：`contains(text1,text2)`
    
    说明：如果text1中包含text2，则返回true；反之，返回false
    
8.  替代函数：
    
    -   “`replace`”：用新值替换正则表达式的第一个匹配项
        
        语法：`replace(number/text/boolean,text1,text2)`
        
        说明：text表示字符串类型，text1表示要代替的值，text2表示新的值
        
    -   "`replaceAll`”：用新值代替正则表达式的所有匹配项
        
        语法：`replaceAll(number/text/boolean,text1,text2)`
        
        说明：text表示字符串类型，text1表示要代替的值，text2表示新的值
        
9.  检验函数（“`test`”）：判断一个字符串是否与正则表达式匹配，返回一个boolean值
    
    语法：`test(number/text/boolean,text)`
    
10.  “验空”函数（”`empty`“）：判断一个值是否为空
    
    语法：`empty(number/text/boolean/date)`
    
    说明：默认情况下，数字为0表示空，字符串以""表示空值，boolean值以false表示空值
    

# 6 六、数学函数

1.  绝对值函数（“`abs`”)：返回一个数的绝对值
    
    语法：`abs(number)`
    
2.  开算术平方根运算（”`sqrt`“）：返回一个数的算术平方根
    
    语法：`sqrt(number)`
    
    说明：number要为非负数
    
3.  开立方根（”`cbrt`“)：返回一个数的立方根
    
    语法：`cbrt(number)`
    
4.  幂次运算（”`^`“或"`pow`"）：将两个数字进行指数运算，并返回它们的值
    
    语法：
    
    -   `number^number`
    -   `pow(number,number)`
    
    补充:
    
    自然指数运算（”`exp`“）：返回e^x的值，其中x为参数，e为常数
    
    语法：`exp(number)`
    
5.  对数运算：notion目前只支持三种对数运算
    
    三 种 对 数 运 算 { l n ( n u m b e r ) 返 回 一 个 数 的 自 然 对 数 l o g 10 ( n u m b e r ) 返 回 这 个 数 以 10 为 底 对 数 的 值 l o g 2 ( n u m b e r ) 返 回 这 个 数 以 2 为 底 对 数 的 值 三种对数运算\begin{cases}ln(number) &返回一个数的自然对数\\log_{10}(number)&返回这个数以10为底对数的值\\log_2(number) &返回这个数以2为底对数的值\end{cases} 三种对数运算⎩⎪⎨⎪⎧​ln(number)log10​(number)log2​(number)​返回一个数的自然对数返回这个数以10为底对数的值返回这个数以2为底对数的值​
    
6.  向上取整函数（“`ceil`”）：返回大于或等于这个数字的最小整数
    
    语法：`ceil(number)`
    
7.  向下取整函数（“`floor`”）：返回小于或等于这个数字的最大整数
    
    语法：`floor(number)`
    
8.  最大/小值函数
    
    -   最大值函数（“`max`”）：返回数的最大值
        
        语法：`max(number1,number2,...)`
        
    -   最小值函数（“`min`”）：返回数的最小值
        
        语法：`min(number1,number2,...)`
        
9.  符号函数（“`sign`”）：返回数的符号，指明数的符号是为正、负或零
    
    语法：`sign(number)`
    
    说明：数字为正时，返回1；数字为负时，返回-1；数字为0时，返回0
    

# 7 七、日期函数

1.  返回时间差函数（`dateBetween`）：返回两个日期之间的时间差，返回值是一个数字。
    
    语法：`dateBetween(date,date,text)`
    
    说明：`date`表示日期；`text`表示”时间差“的基本单位，类型为字符串，取值有：年、季度、月、周、天、小时、分钟、秒、或毫秒。
    
    t e x t 的 取 值 类 型 { " y e a r s " 表 示 以 “ 年 ” 为 基 本 单 位 " q u a r t e r s " 表 示 以 “ 季 ” 为 基 本 单 位 " m o n t h s " 表 示 以 “ 月 " 为 基 本 单 位 " w e e k s " 表 示 以 “ 周 ” 为 基 本 单 位 " d a y s " 表 示 以 “ 天 ” 为 基 本 单 位 " h o u r s " 表 示 以 “ 小 时 ” 为 基 本 单 位 " m i n u t e s " 表 示 以 “ 分 钟 ” 为 基 本 单 位 " s e c o n d s " 表 示 以 “ 秒 ” 为 基 本 单 位 " m i l l i s e c o n d " 表 示 以 “ 毫 秒 ” 为 基 本 单 位 text的取值类型\begin{cases}"years" & 表示以“年”为基本单位\\"quarters"&表示以“季”为基本单位\\"months" &表示以“月"为基本单位\\"weeks"& 表示以“周”为基本单位\\"days"&表示以“天”为基本单位\\"hours"&表示以“小时”为基本单位\\"minutes"&表示以“分钟”为基本单位\\"seconds"&表示以“秒”为基本单位\\"millisecond"&表示以“毫秒”为基本单位\end{cases} text的取值类型⎩⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎨⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎧​"years""quarters""months""weeks""days""hours""minutes""seconds""millisecond"​表示以“年”为基本单位表示以“季”为基本单位表示以“月"为基本单位表示以“周”为基本单位表示以“天”为基本单位表示以“小时”为基本单位表示以“分钟”为基本单位表示以“秒”为基本单位表示以“毫秒”为基本单位​
    
2.  获取当前日期函数（`now`):返回当前的日期和时间
    
    语法：`now()`
    
3.  日期范围开始函数（“`start`”）：返回一个日期范围的开始
    
    语法：`start(date)`
    
4.  日期范围结束函数（“`end`”）：返回一个日期范围的结束
    
    语法：`end(date)`
    
5.  日期到时间戳函数（“`timestamp`”）：返回来自Unix毫秒时间戳的整数，对应于自1970年1月1日起的毫秒数，返回值是`数值`
    
    语法：`timestamp(date)`
    
    说明：把日期格式的`日期转化`为数值类型的`时间戳`
    
6.  时间戳到日期函数（“`fromTimestamp`”）：返回由Unix毫秒时间戳构建的日期，对应于自1970年1月1日起的毫秒数，返回值是`日期`
    
    语法：`fromTimestamp(number)`
    
    说明：把数值类型的`时间戳转化为日期`类型的日期
    
7.  增加日期判据（argument）函数（“`dateAdd`”）：增加到日期，最后一个是单位判据
    
    语法：`dateAdd(date,number,text)`
    
    说明：`date`表示日期；number表示日期差；`text`表示”时间差“的基本单位，类型为字符串，取值有：年、季度、月、周、天、小时、分钟、秒、或毫秒。
    
    t e x t 的 取 值 类 型 { " y e a r s " 表 示 以 “ 年 ” 为 基 本 单 位 " q u a r t e r s " 表 示 以 “ 季 ” 为 基 本 单 位 " m o n t h s " 表 示 以 “ 月 " 为 基 本 单 位 " w e e k s " 表 示 以 “ 周 ” 为 基 本 单 位 " d a y s " 表 示 以 “ 天 ” 为 基 本 单 位 " h o u r s " 表 示 以 “ 小 时 ” 为 基 本 单 位 " m i n u t e s " 表 示 以 “ 分 钟 ” 为 基 本 单 位 " s e c o n d s " 表 示 以 “ 秒 ” 为 基 本 单 位 " m i l l i s e c o n d " 表 示 以 “ 毫 秒 ” 为 基 本 单 位 text的取值类型\begin{cases}"years" & 表示以“年”为基本单位\\"quarters"&表示以“季”为基本单位\\"months" &表示以“月"为基本单位\\"weeks"& 表示以“周”为基本单位\\"days"&表示以“天”为基本单位\\"hours"&表示以“小时”为基本单位\\"minutes"&表示以“分钟”为基本单位\\"seconds"&表示以“秒”为基本单位\\"millisecond"&表示以“毫秒”为基本单位\end{cases} text的取值类型⎩⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎨⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎧​"years""quarters""months""weeks""days""hours""minutes""seconds""millisecond"​表示以“年”为基本单位表示以“季”为基本单位表示以“月"为基本单位表示以“周”为基本单位表示以“天”为基本单位表示以“小时”为基本单位表示以“分钟”为基本单位表示以“秒”为基本单位表示以“毫秒”为基本单位​
    
8.  减少日期的日期函数（`“dateSubtract`”）：减少日期的日期，最后一个是判据
    
    语法：`dateSubtract(date,number,text)`
    
    说明：类似上面的dateAdd函数。
    
9.  设置日期格式函数（“`formatDate`”）：使用“时刻”标准时间格式字符串，设置日期格式，返回的是一个`字符串`
    
    语法：`formatDate(date,text)`
    
    例子：
    
    ```cpp
    formatDate(now(), "MMMM D YYYY, HH:mm") == March 30 2010, 12:00
    formatDate(now(), "YYYY/MM/DD, HH:mm") == 2010/03/30, 12:00
    formatDate(now(), "MM/DD/YYYY, HH:mm") == 03/30/2010, 12:00
    formatDate(now(), "HH:mm A") == 12:00 PM
    formatDate(now(), "M/D/YY") == 3/30/10
    ```
    
10.  返回”给定日期“所用单位函数下的数字
    所 用 的 单 位 函 数 { 分 钟 函 数 （ m i n u t e ） { 返 回 一 个 0 到 59 之 间 的 整 数 ， 对 应 于 给 定 日 期 的 分 钟 数 语 法 ： m i n u t e ( d a t e ) 小 时 函 数 （ h o u r ） { 返 回 一 个 0 到 23 之 间 的 整 数 ， 对 应 于 给 定 日 期 的 小 时 数 语 法 ： h o u r ( d a t e ) 星 期 函 数 （ d a y ） { 返 回 一 个 0 到 6 之 间 的 整 数 ， 对 应 于 给 定 的 日 期 。 0 代 表 星 期 日 ， 1 代 表 星 期 一 等 等 语 法 ： d a y ( d a t e ) 日 期 函 数 （ d a t e ） { 返 回 一 个 1 到 31 之 间 的 整 数 , 对 应 于 给 定 日 期 语 法 ： d a t e ( d a t e ) 月 函 数 （ m o n t h ） { 返 回 一 个 0 到 11 之 间 的 整 数 ， 0 对 应 于 1 月 ， 1 对 应 于 2 月 等 等 语 法 ： m o n t h ( d a t e ) 年 份 函 数 （ y e a r ） { 返 回 给 定 日 期 的 年 份 语 法 ： y e a r ( d a t e ) 所用的单位函数\begin{cases} 分钟函数（minute）\begin{cases}返回一个0到59之间的整数，对应于给定日期的分钟数\\语法：minute(date)\end{cases}\\ 小时函数（hour）\begin{cases}返回一个0到23之间的整数，对应于给定日期的小时数\\语法：hour(date)\end{cases}\\ 星期函数（day）\begin{cases}返回一个0到6之间的整数，对应于给定的日期。0代表星期日，1代表星期一等等\\语法：day(date)\end{cases}\\ 日期函数（date）\begin{cases}返回一个1到31之间的整数,对应于给定日期\\语法：date(date)\end{cases}\\ 月函数（month）\begin{cases}返回一个0到11之间的整数，0对应于1月，1对应于2月等等\\语法：month(date)\end{cases}\\ 年份函数（year）\begin{cases}返回给定日期的年份\\语法：year(date)\\\end{cases} \end{cases} 所用的单位函数⎩⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎨⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎪⎧​分钟函数（minute）{返回一个0到59之间的整数，对应于给定日期的分钟数语法：minute(date)​小时函数（hour）{返回一个0到23之间的整数，对应于给定日期的小时数语法：hour(date)​星期函数（day）{返回一个0到6之间的整数，对应于给定的日期。0代表星期日，1代表星期一等等语法：day(date)​日期函数（date）{返回一个1到31之间的整数,对应于给定日期语法：date(date)​月函数（month）{返回一个0到11之间的整数，0对应于1月，1对应于2月等等语法：month(date)​年份函数（year）{返回给定日期的年份语法：year(date)


# 8 参考资料
自用跳转连接：[ob]()， [blog]()



















