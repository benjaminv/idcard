# 校验身份证合法性，获取身份证详细信息

### 安装:npm install idcard

## [API](#API)

[verify](#verify)

<a name="verify" />
校验身份证合法性，返回boolean值

```js
var idCard = require('idcard');
/**
* param:idcard(string)
* return boolean
*/
idCard.verify('440882199100201232');//false
```

### 身份证中第十八位数字的计算方法

- 将前面的身份证号码17位数分别乘以不同的系数。从第一位到第十七位的系数分别为：7、9、10、5、8、4、2、1、6、3、7、9、10、5、8、4、2； 
- 将这17位数字和系数相乘的结果相加； 
- 用加出来和除以11，看余数是多少
- 余数只可能有0 、1、 2、 3、 4、 5、 6、 7、 8、 9、 10这11个数字。其分别对应的最后一位身份证的号码为1、0、X、9、8、7、6、5、4、3、2； 
- 通过上面得知如果余数是2，就会在身份证的第18位数字上出现罗马数字的Ⅹ。如果余数是10，身份证的最后一位号码就是2。
