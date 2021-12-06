目录
=================

* [Docker运行环境](#docker运行环境)
* [实验题目](#实验题目)
   * [补码与位运算](#补码与位运算)
      * [bitXor(int x, int y)](#bitxorint-x-int-y)
         * [题目说明](#题目说明)
         * [思路1](#思路1)
         * [思路2](#思路2)
      * [tmin()](#tmin)
         * [题目说明](#题目说明-1)
         * [思路](#思路)
      * [isTmax(int x)](#istmaxint-x)
         * [题目说明](#题目说明-2)
         * [思路](#思路-1)
      * [allOddBits(int x)](#alloddbitsint-x)
         * [题目说明](#题目说明-3)
         * [思路](#思路-2)
      * [negate(int x)](#negateint-x)
         * [题目说明](#题目说明-4)
         * [思路](#思路-3)
      * [isAsciiDigit(int x)](#isasciidigitint-x)
         * [题目说明](#题目说明-5)
         * [思路](#思路-4)
      * [conditional(int x, int y, int z)](#conditionalint-x-int-y-int-z)
         * [题目说明](#题目说明-6)
         * [思路](#思路-5)
      * [isLessOrEqual(int x, int y)](#islessorequalint-x-int-y)
         * [题目说明](#题目说明-7)
         * [思路](#思路-6)
      * [logicalNeg(int x)](#logicalnegint-x)
         * [题目说明](#题目说明-8)
         * [思路](#思路-7)
      * [howManyBits(int x)](#howmanybitsint-x)
         * [题目说明](#题目说明-9)
         * [思路](#思路-8)
   * [浮点数](#浮点数)
      * [floatScale2(unsigned uf)](#floatscale2unsigned-uf)
         * [题目说明](#题目说明-10)
         * [思路](#思路-9)
      * [floatFloat2Int(unsigned uf)](#floatfloat2intunsigned-uf)
         * [题目说明](#题目说明-11)
         * [思路](#思路-10)
      * [floatPower2(int x)](#floatpower2int-x)
         * [题目说明](#题目说明-12)
         * [思路](#思路-11)

# Docker运行环境
```c
// 获取 image 镜像
docker pull yansongsongsong/csapp:datalab

// 以交互模式启动容器,在容器内执行/bin/bash命令
docker run -it yansongsongsong/csapp:datalab /bin/bash

// 切换到实验文件目录
cd /root/datalab-handout
```
也可以从官网下载实验文件，编写完成后，放到容器中进行编译和校验实验正确。


# 实验题目
## 补码与位运算
### `bitXor(int x, int y)`
#### 题目说明
使用 `&` 和 `~` 实现 `^` 异或运算


#### 思路1
异或运算的定义如下：

![](https://cdn.nlark.com/yuque/__latex/9c3b789b1867181768a448df665f1368.svg#card=math&code=A%20%5Coplus%20B%20%3D%20%28%5Cneg%20A%20%5Cwedge%20B%29%20%5Cvee%20%28A%20%5Cwedge%20%5Cneg%20B%29&id=rDCvp)

德摩根定律的定义如下：

![](https://cdn.nlark.com/yuque/__latex/911c651169e8226366bfe522bfc70b4f.svg#card=math&code=%5Cneg%28P%20%5Cwedge%20Q%29%20%3D%20%28%5Cneg%20P%29%20%5Cvee%20%28%5Cneg%20Q%29&id=uRhDS)

![](https://cdn.nlark.com/yuque/__latex/d4c57749eb7c130b9ecfe0c5c450c08e.svg#card=math&code=%0A%5Cneg%28P%20%5Cvee%20Q%29%20%3D%20%28%5Cneg%20P%29%20%5Cwedge%20%28%5Cneg%20Q%29&id=pcmXk)


根据分配律和德摩根定律，可以推出：
​

![](https://cdn.nlark.com/yuque/__latex/ad4c56587644638036cc7dda3dbeddf6.svg#card=math&code=%5Cbegin%7Balign%7D%0AA%20%5Coplus%20B%20%26%20%3D%20%28%5Cneg%20A%20%5Cwedge%20B%29%20%5Cvee%20%28A%20%5Cwedge%20%5Cneg%20B%29%20%5C%5C%0A%20%26%20%20%3D%20%28%5Cneg%20A%20%5Cvee%20%28A%20%5Cwedge%20%5Cneg%20B%29%29%20%5Cwedge%20%28B%20%5Cvee%20%28A%20%5Cwedge%20%5Cneg%20B%29%29%20%5C%5C%0A%20%26%20%20%3D%20%28%28%5Cneg%20A%20%5Cvee%20A%29%20%5Cwedge%20%28%5Cneg%20A%20%5Cvee%20%5Cneg%20B%29%29%20%5Cwedge%20%28%28B%20%5Cvee%20A%29%20%5Cwedge%20%28B%20%5Cvee%20%5Cneg%20B%29%29%20%5C%5C%0A%20%26%20%20%3D%20%28%5Cneg%20A%20%5Cvee%20%5Cneg%20B%29%20%5Cwedge%20%28A%20%5Cvee%20B%29%20%5C%5C%0A%20%26%20%20%3D%20%5Cneg%20%28%5Cneg%20A%20%5Cwedge%20%5Cneg%20B%29%20%5Cwedge%20%5Cneg%20%28A%20%5Cwedge%20B%29%0A%5Cend%7Balign%7D&id=YpqCm)


> 特别说明：`A | ~A` 会得到一个全为 1 的二进制数，所以上述可以省略掉



因此：
```c
/* 
 * bitXor - x^y using only ~ and & 
 *   Example: bitXor(4, 5) = 1
 *   Legal ops: ~ &
 *   Max ops: 14
 *   Rating: 1
 */
int bitXor(int x, int y) {
    return ~(~x & ~y) & ~(x & y);
}
```


#### 思路2
在 CSAPP 原书的 2.13 练习题中，提供了 `bis` 位设置和 `bic` 位清除两个指令来实现异或运算，我们可以借鉴其思路来解题。
![Screen Shot 2021-12-03 at 16.45.20.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638521248893-85021c36-bf78-4a81-8ed3-7b6ce4e02293.png#clientId=u9eb7913b-ccd0-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u5d70e07c&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-03%20at%2016.45.20.png&originHeight=1204&originWidth=1546&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1396318&status=done&style=none&taskId=u97ccba40-9ed0-4b2a-a6fa-80bc4c75453&title=)
因此：
```c
/* 
 * bitXor - x^y using only ~ and & 
 *   Example: bitXor(4, 5) = 1
 *   Legal ops: ~ &
 *   Max ops: 14
 *   Rating: 1
 */
int bitXor(int x, int y) {
    int a = x & ~y;
    int b = y & ~x;
    int c = ~a & ~b;
    return ~c;
}
```


### `tmin()`
#### 题目说明
求二进制补码的最小值


#### 思路
对于32位的int型，其补码的取值范围为 -231 ~ 231- 1
​

当二进制补码的最高位为1，其余位为0时，就表示补码的最小值。
​

我们可以定义一个二进制补码 `0x01`，然后左移 31 位就可得到 32 位补码的最小值。
​

```c
/*
 * tmin - return minimum two's complement integer 
 *   Legal ops: ! ~ & ^ | + << >>
 *   Max ops: 4
 *   Rating: 1
 */
int tmin(void) {
    // in 32 mode, tmin = 0x80000000
    return 0x01 << 31;
}
```


### `isTmax(int x)`
#### 题目说明
若x是最大的补码，则返回1；否则，返回0


#### 思路
32 位补码的最大值 `Tmax = 0x7FFFFFFF`，其满足表达式 `x = ~(x + 1)`。
​

除了 `0x7FFFFFFF` 以外，`0xFFFFFFFF` 即 `-1` 也满足该表达式。
​

因为 `~(0xFFFFFFFF) = 0, ~(0x7FFFFFFF) = -1`，所以用表达式 `!!(~x)` 来排除掉 `0xFFFFFFFF`。


```c
/*
 * isTmax - returns 1 if x is the maximum, two's complement number,
 *     and 0 otherwise 
 *   Legal ops: ! ~ & ^ | +
 *   Max ops: 10
 *   Rating: 1
 */
int isTmax(int x) {
    // in 32 mode, tmax = 0x7fffffff
    return !(~(x + 1) ^ x) & !!(~x); // exclude 0xffffffff
}
```


> **💡 小技巧**
> 1. 当遇到表达式位运算需要返回 true / false 时，由于 `!` 运算不为 0 就是 true 的特性，优先考虑有什么特殊表达式的运算结果会是 0，再取 `!` 运算得到 true，模板如下：`return !(expression)`。
> 
> 
> 2. 判断两个数值是否相等时，关系运算符 `a == b` 等价于 `!(a ^ b)`。



### `allOddBits(int x)`
#### 题目说明
给定整数 x，若其二进制形式的奇数位（从前 0 往后 31 编号）均为 1，则返回 1；否则，返回 0。


#### 思路

1. 奇数位均为 1，二进制表示为 `0xAAAAAAAA`，先通过移位得到 `0xAAAAAAAA`




2. 将 `x & 0xAAAAAAAA` 做掩码运算，得到 x 的所有奇数位



3. 判断 x 掩码运算的结果是否等于 `0xAAAAAAAA` 即可



```c
/*
 * allOddBits - return 1 if all odd-numbered bits in word set to 1
 *   where bits are numbered from 0 (least significant) to 31 (most significant)
 *   Examples allOddBits(0xFFFFFFFD) = 0, allOddBits(0xAAAAAAAA) = 1
 *   Legal ops: ! ~ & ^ | + << >>
 *   Max ops: 12
 *   Rating: 2
 */
int allOddBits(int x) {
    // 1111 1111 1111 1111 1111 1111 1111 1101
    // 1010 1010 1010 1010 1010 1010 1010 1010   A B E F
    int mask = 0xAA;
    mask = mask | (mask << 8);  // 0xAAAA
    mask = mask | (mask << 16); // 0xAAAAAAAA
    return !((x & mask) ^ mask);// A ^ A -> 0
}
```


### `negate(int x)`
#### 题目说明
求有符号数 `x` 的相反数 `-x`。


#### 思路
CSAPP 原书中提供了两种计算有符号数相反数的方法：
​


1. 对 x 的每一位求补，再对结果加 1



2. 对 x 的位向量分为两部分，假设 k 是最右边的 1 的位置，对位 k 左边的所有位取反



```c
/*
 * negate - return -x 
 *   Example: negate(1) = -1.
 *   Legal ops: ! ~ & ^ | + << >>
 *   Max ops: 5
 *   Rating: 2
 */
int negate(int x) {
    // chapter 2.3.3: Bit-level representation of two’s-complement negation 
    // 1.complement the bits and then increment the result
    // 2.let k be the position of the rightmost 1, 
    //      complement each bit to the left of bit position k
    return ~x + 1;
}
```




### `isAsciiDigit(int x)`
#### 题目说明
若`0x30` <= x <= `0x39`，则返回1。


#### 思路
将 `0x30` ~ `0x39` 转换成二进制，如下：
```
0x30	110000
0x31  110001
0x32	110010
0x33	110011
0x34	110100
0x35	110101
0x36	110110
0x37	110111
0x38	111000
0x39	111001
```
可以发现：

- 当 x 的高三位是 `110` 时，x 位于 `0x30` ~ `0x39` 之间。
- 当 x 的高五位是 `11100` 时，x 位于 `0x30` ~ `0x39` 之间。



所以，可以先对 x 进行移位，再判断是否等于 `110` 或者 `11100` 即可。
​

```c
/* 
 * isAsciiDigit - return 1 if 0x30 <= x <= 0x39 (ASCII codes for characters '0' to '9')
 *   Example: isAsciiDigit(0x35) = 1.
 *            isAsciiDigit(0x3a) = 0.
 *            isAsciiDigit(0x05) = 0.
 *   Legal ops: ! ~ & ^ | + << >>
 *   Max ops: 15
 *   Rating: 3
 */
int isAsciiDigit(int x) {
    // 00110000 ~ 00111001

    // 00110 000 ~ 00110 111
    // same part: 00110
    int a = (x >> 3) ^ 0x06;

    // 0011100 0 ~ 0011100 1
    // same part: 0011100
    int b = (x >> 1) ^ 0x1c;

    return !a | !b;
}
```


### `conditional(int x, int y, int z)`
#### 题目说明
实现三目运算符 `condition ? branch1 : branch2`。


#### 思路
当 `x != 0` 时，结果为 `y`，可以表示为 `f(x, y, z) = y & 0xFFFFFFFF`
​

当 `x = 0` 时，结果为 `z`，可以表示为 `f(x, y, z) = z & 0xFFFFFFFF`
​

可以用 `~0` 来代表 `0xFFFFFFFF`，即：
​

![](https://cdn.nlark.com/yuque/__latex/df10c81e3a6bc214600dcf59a9b97dda.svg#card=math&code=f%28x%2Cy%2Cz%29%20%3D%0A%5Cbegin%7Bcases%7D%0A%5Csim0%20%5C%20%5C%26%5C%20%20y%2C%20%20%26%20x%20%5Cnot%3D%200%20%5C%5C%0A%5Csim0%20%5C%20%5C%26%5C%20z%2C%20%26%20x%20%3D%200%0A%5Cend%7Bcases%7D&id=ME4MD)
​

当 `x != 0` 时，`!x` 的值为 `0x00`，将 `!x` + `0xFFFFFFFF` 会得到 `0xFFFFFFFF`，所有位都是 1，任何数和该值按位与会保持原有的值
​

当 `x = 0` 时，`!x` 的值为 `0x01`，将 `!x` + `0xFFFFFFFF` 可以使 `!x` 溢出变成 0，所有位都是 0，任何数和该值按位与会变成 0
​

即：
​

![](https://cdn.nlark.com/yuque/__latex/bd0dc01b4e8981cfa6cb3991b8027665.svg#card=math&code=%21x%20%2B%20%5Csim0%20%3D%0A%5Cbegin%7Bcases%7D%0A%5Csim0%2C%20%20%26%20x%20%5Cnot%3D%200%20%5C%5C%0A0%2C%20%26%20x%20%3D%200%0A%5Cend%7Bcases%7D&id=LQB9q)


```c
/*
 * conditional - same as x ? y : z 
 *   Example: conditional(2,4,5) = 4
 *   Legal ops: ! ~ & ^ | + << >>
 *   Max ops: 16
 *   Rating: 3
 */
int conditional(int x, int y, int z) {
    // when x != 0 => y & 0xffffffff
    // when x  = 0 => z & 0xffffffff
    // ~0 => 0xffffffff

    int flag = !x + ~0;
    // x != 0 => flag = 0xffffffff = -1
    // x  = 0 => flag = 0x00000000 = 0

    return (flag & y) | (~flag & z);
}
```


### `isLessOrEqual(int x, int y)`
#### 题目说明
实现 `x <= y`。


#### 思路
当 x 和 y 的符号不相同时，x 必须是负数，即 `x < 0 <= y`
​

当 x 和 y 的符号相同时，对不等式移项，得 `y + (-x) >= 0`
​

> **💡 小技巧**
> 1. 如何判断一个整数是正数还是负数呢？
> 
>     对于 32 位的 int 型整数，右移 31 位，若结果为 0，则为正数；若结果为 -1，则为负数。
> 
>
> 2. 如何判断两个整数的符号位是否相同呢？
> 
>     将两个整数分别右移 31 位，再进行异或运算，若结果为 0，则符号位相同；若结果为 1，则符号位不同



```c
/*
 * isLessOrEqual - if x <= y  then return 1, else return 0 
 *   Example: isLessOrEqual(4,5) = 1.
 *   Legal ops: ! ~ & ^ | + << >>
 *   Max ops: 24
 *   Rating: 3
 */
int isLessOrEqual(int x, int y) {
    // different sign => x < 0 <= y
    // same sign => y + (-x) >= 0

    // if variable >= 0 then sign = 0(0x00000000)
    // if variable < 0 then sign = -1(0xffffffff)
    int sign_x = x >> 31;
    int sign_y = y >> 31;

    // diff sign = 0xffffffff  same sign = 0x00000000
    int is_diff_sign = sign_x ^ sign_y;

    // is_diff_sign = 0xffffffff
    // x must < 0 => sign_x = 0xffffffff
    int diff_sign = !!(is_diff_sign & sign_x);

    // -x
    int negate_x = ~x + 1;

    // y + (-x) >= 0
    // if condition meet sign_y_minus_x = 0 else sign_y_minus_x = -1(0xffffffff)
    int sign_y_minus_x = (y + negate_x) >> 31;

    // is_diff_sign = 0x00000000
    // sign_y_minus_x = 0x00000000
    int same_sign = (!is_diff_sign) & (!sign_y_minus_x);

    return diff_sign | same_sign;
}
```


### `logicalNeg(int x)`
#### 题目说明
实现逻辑非!运算；x = 0 时返回 1，其他的都返回 0。


#### 思路
0 和其相反数 0 进行按位或操作，结果的符号位为 0；除 0 以外，任何一个数和它的相反数进行按位或操作，结果的符号位为 1。
​

所以：

1. 计算 x 的相反数 ~x



2. 将 x 与其相反数 ~x 进行按位或运算，再右移 31 位，得到的结果为 0 或 -1

   ![image.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638539466668-eba8e8fb-baed-41f9-bbc0-8aa23242764b.png#clientId=u824abc94-d7ce-4&crop=0&crop=0&crop=1&crop=1&from=drop&height=65&id=u974a5a74&margin=%5Bobject%20Object%5D&name=image.png&originHeight=100&originWidth=556&originalType=binary&ratio=1&rotation=0&showTitle=false&size=14348&status=done&style=none&taskId=u673bf7d1-6905-4eab-8f3e-434edada569&title=&width=364)
> 补码的右移是算术右移，所以符号位为 1 时，右移 31 位得到的二进制位是 `0xFFFFFFFF`，即 `-1`



3. 将步骤2得到的结果加 1 即可

![Screen Shot 2021-12-03 at 21.51.57.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638539526445-cfba6023-7250-422b-9b08-95ab5d19c77a.png#clientId=u824abc94-d7ce-4&crop=0&crop=0&crop=1&crop=1&from=ui&height=46&id=u6d452b7b&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-03%20at%2021.51.57.png&originHeight=60&originWidth=450&originalType=binary&ratio=1&rotation=0&showTitle=false&size=9614&status=done&style=none&taskId=u8ee7e05a-6222-4e4f-9526-70f41a50657&title=&width=344)
```c
/* 
 * logicalNeg - implement the ! operator, using all of 
 *              the legal operators except !
 *   Examples: logicalNeg(3) = 0, logicalNeg(0) = 1
 *   Legal ops: ~ & ^ | + << >>
 *   Max ops: 12
 *   Rating: 4 
 */
int logicalNeg(int x) {
    int negate_x = ~x + 1;
    int sign_x = (x | negate_x) >> 31;
    return sign_x + 1;
}
```


### `howManyBits(int x)`
#### 题目说明
返回在二补数中表示 x 所需的最小位数


#### 思路
正数的补码：正数最高位的1为第n个数，再加上符号位，结果为n+1。
​

负数的补码：转换为正数，同上。


```c
/* howManyBits - return the minimum number of bits required to represent x in
 *             two's complement
 *  Examples: howManyBits(12) = 5
 *            howManyBits(298) = 10
 *            howManyBits(-5) = 4
 *            howManyBits(0)  = 1
 *            howManyBits(-1) = 1
 *            howManyBits(0x80000000) = 32
 *  Legal ops: ! ~ & ^ | + << >>
 *  Max ops: 90
 *  Rating: 4
 */
int howManyBits(int x) {
    int b16, b8, b4, b2, b1;

    int sign = x >> 31;

    x = (sign & ~x) | (~sign & x); //如果为正数，保持不变；如果为负数，按位取反

    // 判断高16位是否存在1, 如果存在, 则b16 = 16, 否则为0
    b16 = (!!(x >> 16)) << 4;
    x = x >> b16; //如果高16位存在1, x右移16位舍弃低16位, 在新的低16位继续查找; 否则保持不变

    // 判断高8位
    b8 = (!!(x >> 8)) << 3;
    x = x >> b8;

    // 判断高4位
    b4 = (!!(x >> 4)) << 2;
    x = x >> b4;

    // 判断高2位
    b2 = (!!(x >> 2)) << 1;
    x = x >> b2;

    // 判断高1位
    b1 = (!!(x >> 1));
    x = x >> b1;

    // 低1位 + 符号位
    return b16 + b8 + b4 + b2 + b1 + x + 1;
}
```


## 浮点数
### `floatScale2(unsigned uf)`
#### 题目说明
计算输入被解释为浮点数的值 uf * 2


#### 思路

1. 先通过掩码运算，得到浮点数的 `E`阶码、`M`尾数、`s`符号



2. 判断 `exp` 是否等于 `ffffffff`，如果是，则返回 uf



3. 判断 `exp` 是否等于 `00000000`，表示非规格化值，将 frac * 2 即可



4. 其他情况下表示规格化值，uf * 2 可以解释为将 uf 的阶码 `E` + 1
```c
/* 
 * floatScale2 - Return bit-level equivalent of expression 2*f for
 *   floating point argument f.
 *   Both the argument and result are passed as unsigned int's, but
 *   they are to be interpreted as the bit-level representation of
 *   single-precision floating point values.
 *   When argument is NaN, return argument
 *   Legal ops: Any integer/unsigned operations incl. ||, &&. also if, while
 *   Max ops: 30
 *   Rating: 4
 */
unsigned floatScale2(unsigned uf) {
    // 0 ffff ffff 000 0000 0000 0000 0000 0000
    int exp_mask = 0xFF << 23;
    // 0000 0000 0111 1111 1111 1111 1111 1111
    int frac_mask = 0x7FFFFF;
    // 1 000 0000 0000 0000 0000 0000 0000 0000
    int sign_mask = 0x01 << 31;

    int sign = uf & sign_mask;  // extract sign bit
    int exp = uf & exp_mask;    // extract exp  bit
    int frac = uf & frac_mask;  // extract frac bit

    // when argument is NaN, return argument
    if (exp == (exp_mask)) {
        return uf;
    }

    // Denormalized => exp = 0
    if (exp == 0) {
        return sign | (frac << 1);
    }

    // Normalized => 0 < exp < exp_mask
    // uf's exp + 1
    return uf + (0x01 << 23);
}
```


### `floatFloat2Int(unsigned uf)`
#### 题目说明
将输入被解释为浮点数的值 uf 转换成 int 类型


#### 思路

1. 先通过掩码运算，得到浮点数的 `E`阶码、`M`尾数、`s`符号



2. 再根据 `E`、`M` 来转换 `int`



3. 最后考虑符号位 `s`



```c
/*
 * floatFloat2Int - Return bit-level equivalent of expression (int) f
 *   for floating point argument f.
 *   Argument is passed as unsigned int, but
 *   it is to be interpreted as the bit-level representation of a
 *   single-precision floating point value.
 *   Anything out of range (including NaN and infinity) should return
 *   0x80000000u.
 *   Legal ops: Any integer/unsigned operations incl. ||, &&. also if, while
 *   Max ops: 30
 *   Rating: 4
 */
int floatFloat2Int(unsigned uf) {
    // 0 ffff ffff 000 0000 0000 0000 0000 0000
    int exp_mask = 0xFF << 23;
    // 0000 0000 0111 1111 1111 1111 1111 1111
    int frac_mask = 0x7FFFFF;
    // 1 000 0000 0000 0000 0000 0000 0000 0000
    int sign_mask = 0x01 << 31;

    int sign = uf & sign_mask;  // extract sign bit
    int exp = uf & exp_mask;    // extract exp  bit
    int frac = uf & frac_mask;  // extract frac bit
    int E = (exp >> 23) - 127;  // E = exp - bias, bias = (2^(k - 1)) - 1, k = 8
    int M = frac + (1 << 23);   // M = 1 + f

    if (E < 0) return 0;
    if (E > 31) return 0x80000000u;

    if (E <= 23) { // 右移舍弃小数部分
        M >>= (23 - E);
    } else {       // 左移补0
        M <<= (E - 23);
    }

    return sign ? ~M + 1 : M;
}
```


### `floatPower2(int x)`
#### 题目说明
使用位运算求 2.0x​


#### 思路
可以将 2.0x 看成 1.0 * 2x，则有：
```c
bias = 127, E = x, 则 exp = x + 127
M = 1.0, 则 frac = 0
```
因此：
```c
/*
 * floatPower2 - Return bit-level equivalent of the expression 2.0^x
 *   (2.0 raised to the power x) for any 32-bit integer x.
 *
 *   The unsigned value that is returned should have the identical bit
 *   representation as the single-precision floating-point number 2.0^x.
 *   If the result is too small to be represented as a denorm, return
 *   0. If too large, return +INF.
 * 
 *   Legal ops: Any integer/unsigned operations incl. ||, &&. Also if, while 
 *   Max ops: 30 
 *   Rating: 4
 */
unsigned floatPower2(int x) {
    // 2.0^x -> 1.0*2^x
    // signal bit = 0
    // exp = E + bias
    // bias = 2^(k-1) - 1 = 127
    // M = 1 + frac
    // frac = 0
    int INF = 0xFF << 23;

    int exp = x + 127; // exp = E + bias

    // 1 <= exp <= 254
    if (exp <= 0) {
        return 0;
    }
    if (exp >= 0xFF) {
        return INF;
    }

    // 0 exp 00000000000000000000000
    return exp << 23; // signal bit = 0
}
```

