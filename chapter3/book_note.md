## Intel CPU
### `x86` 与 `x86-64`
因为 Intel 第一代芯片为 `8086`，所以 Intel 处理器整个系列俗称 `x86`；对于 IA32 的 64 位扩展的实现，即称为 `x86-64`。


### 摩尔定律
芯片上的晶体管数据每18个月翻一倍。
![Screen Shot 2021-12-09 at 20.56.59.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639054632197-f5f71e72-fac4-4cd6-bf5d-c8f5de1b520f.png#clientId=u501b9864-3c92-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ua757faa8&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-09%20at%2020.56.59.png&originHeight=712&originWidth=1232&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1119014&status=done&style=none&taskId=uff007e80-b4c0-47d9-aa03-b74cfd550a4&title=)




## 机器级代码
### C、汇编和机器码的关系
![Screen Shot 2021-12-09 at 20.44.09.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639054898530-aa027c49-5d34-4df7-a0c8-d1d2c2b1f3b8.png#clientId=u501b9864-3c92-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u0bf0c29c&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-09%20at%2020.44.09.png&originHeight=942&originWidth=2250&originalType=binary&ratio=1&rotation=0&showTitle=false&size=601441&status=done&style=none&taskId=ue3ad859f-a518-4d75-8a06-88d56f5710f&title=)


### 编译器
GCC C 编译器，用来将 C 程序编译成汇编代码，最终生成可执行的二进制文件。

| 参数 | 说明 | 举例 |
| --- | --- | --- |
| -Og | 告诉编译器使用会生成符合原始C代码整体结构的机器代码的优化级别，适合作为学习工具和调试 | `gcc -Og -o p abc.c def.c` |
| -O1/-O2 | 较高的优化级别，能优化程序性能，优化产生的代码会严重变形，无法理解 | `gcc -O1 -o p xyz.c` |
| -o [name] | 指定最终的可执行代码文件名 | `gcc -O2 -o p xyz.c` |
| -S | 编译器只产生汇编文件，不做进一步的工作 | `gcc -Og -S xyz.c` |
| -masm=intel | 使用Intel的汇编代码格式 | `gcc -Og -S -masm=intel xyz.c` |

> 💡 小知识
> 二进制目标文件可使用 GDB\LLDB 查看16进制序列

### 汇编代码示例
![Screen Shot 2021-12-09 at 21.28.41.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639056530254-8766abdc-2a86-4335-b5b8-0775ef477e53.png#clientId=u501b9864-3c92-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u112c61b3&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-09%20at%2021.28.41.png&originHeight=350&originWidth=1528&originalType=binary&ratio=1&rotation=0&showTitle=false&size=310965&status=done&style=none&taskId=u5bc3cb72-57bb-4fe5-b9b1-2a4ca436108&title=)
![Screen Shot 2021-12-09 at 21.27.36.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639056536916-408aa773-950d-48ea-a131-87dd38c0d381.png#clientId=u501b9864-3c92-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u82737ac5&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-09%20at%2021.27.36.png&originHeight=1420&originWidth=1526&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1248836&status=done&style=none&taskId=uc067d0bf-1392-4c21-b357-ea846281885&title=)


### 反汇编器
根据机器代码产生一种类似汇编代码的格式，Linux 中用 `objdump -d` 可以实现。
![Screen Shot 2021-12-09 at 21.16.19.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639055786885-ccaff596-c0c5-449f-9cdb-761780a2e63e.png#clientId=u501b9864-3c92-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=qP7VO&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-09%20at%2021.16.19.png&originHeight=536&originWidth=1294&originalType=binary&ratio=1&rotation=0&showTitle=false&size=599207&status=done&style=none&taskId=uddddcd1d-4543-4b42-9dc1-39489f223d7&title=)
> ⚠️ 注意事项
> 反汇编器生成的指令命名规则与 GCC 生成的汇编代码使用的有些细微差别，体现在很多指令结尾的 `q`​



## 数据格式
### 字长
Intel用术语 "`字(word)`" 表示 16 位数据类型。因此，32 位数为 "`双字(double words)`"，64 位数为 "`四字(quad words)`"。
![Screen Shot 2021-12-09 at 21.37.54.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639057085883-05faa2f5-a274-4872-81c2-bc6307381d0a.png#clientId=u501b9864-3c92-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u964118ee&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-09%20at%2021.37.54.png&originHeight=584&originWidth=1328&originalType=binary&ratio=1&rotation=0&showTitle=false&size=100896&status=done&style=none&taskId=u00ef699f-cdbb-4aeb-ae0f-3431df3d713&title=)
### 通用目的寄存器
`x86-64` 的 CPU 包含一组 16 个存储 64 位值的通用目的寄存器，这些寄存器用来存储整数数据和指针。
![Screen Shot 2021-12-09 at 21.37.43.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639057093669-d88b8efd-f5dd-4e59-9b68-a21f8af9926d.png#clientId=u501b9864-3c92-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ua1e3f61b&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-09%20at%2021.37.43.png&originHeight=1640&originWidth=1362&originalType=binary&ratio=1&rotation=0&showTitle=false&size=283273&status=done&style=none&taskId=u39eb96f5-8685-4533-bfb7-2ba2b1e74f0&title=)

- 指令可以对这16个寄存器的低位字节中存放的不同大小的数据进行操作
  - 字节级操作可以访问最低的字节，如 `%ax`、`%bx`
  - 16 位操作可以访问最低的 2 个字节，如 `%bp`、`%si`
  - 32 位操作可以访问最低的 4 个字节，如 `%eax`、`%exi`
  - 64 位操作可以访问整个寄存器，如 `%rax`、`%rdx`



> 💡** 特别说明**
> **  **
> **对于生成小于 8 字节结果的指令，寄存器中剩下的字节会怎么样？**
> 1. 生成 1 字节和 2 字节数字的指令会保持剩下的字节不变
> 1. 生成 4 字节数字的指令会把高位 4 个字节置为 0

​

##### 调用者保存 & 被调用者保存
![Screen Shot 2021-12-10 at 08.06.37.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639094867349-b2ba6ab9-4cf9-423a-b647-51bbf13925ca.png#clientId=u2ad51de9-0cfd-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ub0350fa9&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-10%20at%2008.06.37.png&originHeight=760&originWidth=1574&originalType=binary&ratio=1&rotation=0&showTitle=false&size=410481&status=done&style=none&taskId=u00ec745f-84f7-40c4-9c22-da70fc67982&title=)


### 操作数类型
##### (1) 立即数
immediate，表示常量值。
​

书写方式是 `$` 后面跟一个用标准 C 表示法表示的整数。如 `$-577`、`$0x1F`。
​

不同的指令运行的立即数值范围不同，汇编器会自动选择最紧凑的方式进行数值编码。


##### (2) 寄存器
表示某个寄存器存储的内容。
![Screen Shot 2021-12-09 at 21.59.19.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639058460195-d8964267-2dba-414c-b355-fb09c95e7614.png#clientId=u501b9864-3c92-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u5bc092ac&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-09%20at%2021.59.19.png&originHeight=156&originWidth=1372&originalType=binary&ratio=1&rotation=0&showTitle=false&size=160470&status=done&style=none&taskId=ufbfd24a6-f01c-4421-9ea4-b370bfa0b5f&title=)


##### (3) 内存引用
根据计算出来的有效地址，访问某个内存位置，获取其中存储的内容。
​

通用形式及地址计算如下：
![Screen Shot 2021-12-09 at 22.05.18.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639058744705-15687273-0fe9-4567-826f-572930af0921.png#clientId=u501b9864-3c92-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u65966f78&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-09%20at%2022.05.18.png&originHeight=702&originWidth=1264&originalType=binary&ratio=1&rotation=0&showTitle=false&size=283761&status=done&style=none&taskId=ua1aece0c-243e-492a-a43c-081602fb757&title=)
> **💡 特别说明**
>
> 1. 基址和变址寄存器都必须是 64 位寄存器。
>
​

> 2. 比例因子的取值是与源代码中定义的数组类型的字节是相关的，编译器会根据数据的类型的字节长度来确定比例因子的数值。
>
​

> 3. 内存引用数组元素时，会使用通用形式，其他形式都是通用形式的特殊情况/变形。



##### (4) 总结
![Screen Shot 2021-12-09 at 22.14.32.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639059308560-32c3ca02-ab31-4065-a858-482ef1c16116.png#clientId=u501b9864-3c92-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u48a44372&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-09%20at%2022.14.32.png&originHeight=812&originWidth=1376&originalType=binary&ratio=1&rotation=0&showTitle=false&size=171961&status=done&style=none&taskId=u95d2b875-0d11-49fc-b46a-af2d8b3c5ca&title=)
### 数据传送指令
##### (1) 常规传送 - MOV 类
把数据从源位置复制到目的位置，不做任何改变。
​

MOV 类有 4 条指令组成：`movb`、`movw`、`movl` 和 `movq`，4 条指令都执行相同操作，区别在于操作的数据大小不同：分别是 1、2、4 和 8 字节。
​

源操作数指定的值可以是立即数、寄存器或者内存引用，目的操作数指定的位置是寄存器或者内存地址引用。
![Screen Shot 2021-12-10 at 07.34.05.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639092877425-d93a6ec8-e067-4fda-bac9-273078f3950b.png#clientId=u2a9ce04f-2a93-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u64400ec1&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-10%20at%2007.34.05.png&originHeight=488&originWidth=970&originalType=binary&ratio=1&rotation=0&showTitle=false&size=70047&status=done&style=none&taskId=u6ee3607c-8f50-46ba-8e9d-6e68975b193&title=)
> **💡 特别说明**
>
> 1. 传送指令的两个操作数不能都指向内存位置，将一个值从内存位置复制到另一个内存位置需要两条指令：第一条指令将源值从内存加载到寄存器中，第二条将该寄存器值写入目标内存位置。
>
​

> 2. 寄存器部分的大小必须与指令最后一个字符(b/w/l/q)指定的大小匹配。
>
​

> 3. `movl` 指令以寄存器作为目的时，它会把该寄存器的高位 4 字节设置为0。
>
​

> 4. 常规的 `movq` 指令只能以表示为 32 位补码数字的立即数作为源操作数，然后将这个值符号扩展得到 64 位的值，放到目的位置。
>
​

> 5. `movabsq` 指令能够以任意 64 位立即数值作为源操作数，并且只能以寄存器作为目的。



##### (2) 特殊传送 - MOVZ & MOVS 类
MOVZ 和 MOVS 两类数据移动指令，在将较小的源值复制到较大的目的时使用，所有这些指令都把数据从源(寄存器或内存) 复制到目的寄存器。
​

MOVZ 类的指令把目的中剩余的字节填充为0，即零扩展。
![Screen Shot 2021-12-10 at 07.43.47.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639093552578-824df8f0-c40f-4e72-8563-24ede99198e1.png#clientId=u2a9ce04f-2a93-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u4afcec11&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-10%20at%2007.43.47.png&originHeight=510&originWidth=1340&originalType=binary&ratio=1&rotation=0&showTitle=false&size=111862&status=done&style=none&taskId=ubec10442-7b1e-43f5-90d2-036e89178a7&title=)
​

MOVS 类的指令通过符号扩展来填充，把源操作数的最高位进行复制，即符号位扩展。
![Screen Shot 2021-12-10 at 07.43.57.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639093561843-c6df9cdd-f2b9-44f7-965d-2c770a14b800.png#clientId=u2a9ce04f-2a93-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ue33b46fb&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-10%20at%2007.43.57.png&originHeight=678&originWidth=1504&originalType=binary&ratio=1&rotation=0&showTitle=false&size=163666&status=done&style=none&taskId=u0c59db2d-0aca-4e07-8519-57afee85972&title=)
​

每条指令名字的最后两个字符都是大小指示符：第一个字符指定源的大小，第二个指明目的的大小。
​

##### (3) 出入栈指令 - `pushq` & `popq`
###### 栈是一种后进先出的数据结构，通过 `push` 操作将数据压入栈中，通过 `pop` 操作删除数据。


程序栈存放在内存中某个区域，栈向下增长，栈顶元素的地址是所有栈中元素地址中最低的。
![Screen Shot 2021-12-10 at 07.52.32.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639093962640-befcebfe-b8c5-4f02-b876-7fd39ab05d59.png#clientId=u2a9ce04f-2a93-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u5227866d&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-10%20at%2007.52.32.png&originHeight=690&originWidth=1134&originalType=binary&ratio=1&rotation=0&showTitle=false&size=539617&status=done&style=none&taskId=u34fe6caa-bd82-4ecd-b938-e0ba95b15cc&title=)
​

寄存器 `%rsp` 表栈指针保存着栈顶元素的地址，栈操作指令都只有一个操作数：将入的数据源和弹出的数据目的。
​

`pushq` 指令是把数据压入到栈上，其操作是：首先将栈指针减 8，然后将值写到新的栈顶地址。指令如下：
```c
pushq %rbp

// 上面的指令等价于
subq $8,%rsp     // decrement stack pointer
movq %rbp,(%rsp) // store %rbp on stack
```
`popq` 指令是弹出数据，其操作是：从栈顶位置读出数据，然后将栈指针加 8。指令如下：
```c
popq %rax

// 上面的指令等价于
movq (%rsp),%rax // read %rax from stack
addq $8,%rsp     // increment stack pointer
```
要注意的是，被弹出的值仍然会保持在内存位置中，直到被覆盖。
​

## 算术逻辑指令
整数和逻辑操作主要有四组：加载有效地址、一元操作、二元操作和移位，每组指令类都有对四种不同大小数据的指令。
![Screen Shot 2021-12-10 at 16.40.18.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639125632479-e3b97790-4f59-4ed0-b5e2-11e328b4a9e8.png#clientId=ua256d11a-9e8b-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u9d0b3d3f&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-10%20at%2016.40.18.png&originHeight=1044&originWidth=1210&originalType=binary&ratio=1&rotation=0&showTitle=false&size=197505&status=done&style=none&taskId=uec5f70ec-9366-4600-b6af-eeff05cea76&title=)
### 加载有效地址 `leaq`
![Screen Shot 2021-12-10 at 16.51.19.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639126323258-1fa0288a-b8ee-4fb3-8d17-5b85f6a42302.png#clientId=ua256d11a-9e8b-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ud0d472d1&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-10%20at%2016.51.19.png&originHeight=62&originWidth=888&originalType=binary&ratio=1&rotation=0&showTitle=false&size=13806&status=done&style=none&taskId=u79939b05-742e-41f3-897a-9fd659f78d4&title=)
`leaq` 指令是从内存读数据到寄存器。实际应用有 2 个：

1. 将有效地址写入到目的操作数，为后面的内存应用产生指针；
1. 描述普通的算术操作，执行加法和有限形式的乘法。

![Screen Shot 2021-12-10 at 16.49.36.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639126185867-1bfe1e02-86a5-4d45-bd61-5b07ba46fdb3.png#clientId=ua256d11a-9e8b-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u55bfe770&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-10%20at%2016.49.36.png&originHeight=996&originWidth=1432&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1411848&status=done&style=none&taskId=u84525d3e-2f00-4ab8-b4d4-0bb255ab9d6&title=)


### 一元操作
![Screen Shot 2021-12-10 at 16.51.25.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639126333525-d55758a8-ff68-4c91-acb8-a6fe679eaa8d.png#clientId=ua256d11a-9e8b-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u4ede31e6&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-10%20at%2016.51.25.png&originHeight=176&originWidth=884&originalType=binary&ratio=1&rotation=0&showTitle=false&size=28043&status=done&style=none&taskId=u66a7b171-ab10-4c7a-be52-da8e51334b5&title=)
一元操作，只有一个操作数，既是源又是目的；
​

操作数可以是寄存器或者内存引用。


### 二元操作
![Screen Shot 2021-12-10 at 16.51.31.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639126383567-5c1c3ad2-8dd5-4bdd-92f0-1faff51e20dc.png#clientId=ua256d11a-9e8b-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u600c16e4&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-10%20at%2016.51.31.png&originHeight=264&originWidth=898&originalType=binary&ratio=1&rotation=0&showTitle=false&size=42822&status=done&style=none&taskId=ud5fe6447-2461-48d8-9063-d047317d70a&title=)
二元操作，第二个操作数既是源又是目的；
​

第一个操作数可以是立即数、寄存器或内存引用；
​

第二个操作数可以是寄存器或内存引用。


### 移位
![Screen Shot 2021-12-10 at 16.51.38.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639126471705-217c0cd3-df39-45b7-a4df-e811f6eb8381.png#clientId=ua256d11a-9e8b-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u1d59670b&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-10%20at%2016.51.38.png&originHeight=170&originWidth=894&originalType=binary&ratio=1&rotation=0&showTitle=false&size=36420&status=done&style=none&taskId=uc3d7b1e2-87c7-4edc-8469-fe8364fd252&title=)
![Screen Shot 2021-12-10 at 16.56.41.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639126609762-8382a939-5706-4d30-b888-c683d6b2a573.png#clientId=ua256d11a-9e8b-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u473c1e38&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-10%20at%2016.56.41.png&originHeight=366&originWidth=1410&originalType=binary&ratio=1&rotation=0&showTitle=false&size=726475&status=done&style=none&taskId=uec7204bf-ef0c-410c-8e5a-cd402b83211&title=)


### 特殊算术指令
![Screen Shot 2021-12-10 at 17.01.55.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639126925182-594c98b9-f836-44cb-9639-7607cb87abd5.png#clientId=ua256d11a-9e8b-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ub5d8d3d5&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-10%20at%2017.01.55.png&originHeight=626&originWidth=1442&originalType=binary&ratio=1&rotation=0&showTitle=false&size=851034&status=done&style=none&taskId=u04983b50-043c-451c-a670-48fcba425f6&title=)
## 控制
### 条件码寄存器
![截屏2021-12-16 22.04.33.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639663482050-6630ff81-e82b-4e84-9d3e-f98822f9a60d.png#clientId=ub97c1cda-a905-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u8e564d06&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-16%2022.04.33.png&originHeight=430&originWidth=1516&originalType=binary&ratio=1&rotation=0&showTitle=false&size=715238&status=done&style=none&taskId=ub6ca8328-36a2-4692-82fd-20799f8dc4c&title=)
![条件码.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639663490007-1b66ca84-6270-4769-8d6b-b9242ea17553.png#clientId=ub97c1cda-a905-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u1aef969e&margin=%5Bobject%20Object%5D&name=%E6%9D%A1%E4%BB%B6%E7%A0%81.png&originHeight=918&originWidth=1432&originalType=binary&ratio=1&rotation=0&showTitle=false&size=256333&status=done&style=none&taskId=u0d96600f-50df-40e1-96d4-05c7978b61c&title=)


### 条件码设置
有三类指令可以设置条件码。
​

##### (1) 除 `leaq` 指令外的算术逻辑指令
![Screen Shot 2021-12-10 at 16.40.18.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639663759367-3676832f-46d8-43f3-9e09-4f1a295665a1.png#clientId=ub97c1cda-a905-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ua2697cd7&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-10%20at%2016.40.18.png&originHeight=1044&originWidth=1210&originalType=binary&ratio=1&rotation=0&showTitle=false&size=196202&status=done&style=none&taskId=u1e0d66b5-5067-4b92-b734-05cb2d6ab10&title=)


##### (2) CMP 指令
该指令与 SUB 指令行为一样，根据两个操作数的差来设置条件码；只设置条件码，不改变任何其他寄存器。
​

##### (3) TEST 指令
该指令与 AND 指令行为一样，根据两个操作数按位与的结果来设置条件码；只设置条件码，不改变任何其他寄存器。
​

![截屏2021-12-16 22.15.33.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639664208132-5285ba82-fd6c-4026-92d1-2cc044070d4f.png#clientId=ub97c1cda-a905-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ub116b998&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-16%2022.15.33.png&originHeight=598&originWidth=898&originalType=binary&ratio=1&rotation=0&showTitle=false&size=80453&status=done&style=none&taskId=u1e729be5-853a-4e52-ae82-9b1ecc3cd8e&title=)


### 条件码访问
条件码通常不会直接读取，常用的使用方法有三种：

1. 根据条件码的某种组合，将一个字节设置为 0 或 1（SET 指令）
1. 条件跳转到程序的某个其他的部分（jump 指令）
1. 有条件地传送数据（CMOV 指令）

​

#### SET 指令
一条 SET 指令的目的操作数是低位单字节寄存器（如 `%al`、`%bl` 等），或是一个字节的内存位置，指令会将这个字节设置为 0 或 1。
![截屏2021-12-17 16.35.19.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639730127678-23151554-9176-4533-9211-240cf726d792.png#clientId=u3ca5926d-460e-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u7ae70a32&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-17%2016.35.19.png&originHeight=872&originWidth=1134&originalType=binary&ratio=1&rotation=0&showTitle=false&size=775357&status=done&style=none&taskId=u7a8cc3d8-5c5f-43bf-8516-74956a73e83&title=)
#### CMOV 条件传送指令
每条指令都有两个操作数：寄存器或者内存地址S，和目的寄存器R；指令的结果取决于条件码的值。
​

源值可以从内存或者寄存器中读取，但是只有在指定的条件满足时，才会被复制到目的寄存器中。
​

源和目的的值可以是 16、32、64 位长，不支持单字节的条件传送。
![截屏2021-12-17 21.42.16.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639748543292-f30d7eab-a1f0-48d2-a08c-55c6d3bccd7d.png#clientId=u046d2332-4cce-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ud1497175&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-17%2021.42.16.png&originHeight=660&originWidth=976&originalType=binary&ratio=1&rotation=0&showTitle=false&size=584713&status=done&style=none&taskId=ua3e51f9c-6c5c-4dec-a7a0-885a3c4e665&title=)


### 跳转指令
跳转指令会导致执行切换到程序中一个全新的位置。
![截屏2021-12-17 16.38.19.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639730309871-9d238d5e-4aab-4974-b711-c35a754b3680.png#clientId=u3ca5926d-460e-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u64ba9070&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-17%2016.38.19.png&originHeight=664&originWidth=1122&originalType=binary&ratio=1&rotation=0&showTitle=false&size=704140&status=done&style=none&taskId=ucc60f21c-d661-4f53-bbc5-da604293cf5&title=)
`jmp` 指令是无条件跳转，它可以是直接跳转，即跳转目标是作为指令的一部分编码的；
也可以是间接跳转，即跳转目标是从寄存器或内存位置中读出的。
​

其他的跳转指令都是有条件的，他们根据条件码的某种组合，当满足跳转条件时进行跳转，当条件不满足时，继续执行执行代码序列中下一条指令。
​

### 条件分支
![截屏2021-12-17 21.38.19.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639748554576-81e5f388-900d-483a-a888-9eab47631bc3.png#clientId=u046d2332-4cce-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u53e72d5e&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-17%2021.38.19.png&originHeight=1676&originWidth=3432&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1007468&status=done&style=none&taskId=ub11cfbd7-03b2-4ea7-a67a-6a147a269d3&title=)
> 条件传送实现条件分支，在C语言中表现为三元表达式 `test ? then : else`

![截屏2021-12-17 21.45.09.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639748720661-f4fc3177-8d48-48e9-b7c7-6912affade4c.png#clientId=u046d2332-4cce-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u060101bc&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-17%2021.45.09.png&originHeight=606&originWidth=1194&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1059818&status=done&style=none&taskId=ueac7e603-6ca8-4c69-aff9-28c4db3d5b4&title=)


#### 条件传送的 Bad Cases
![截屏2021-12-17 21.46.28.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639748798032-9ef5023a-637c-424b-8c89-5614b97a5c56.png#clientId=u046d2332-4cce-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u83a0783d&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-17%2021.46.28.png&originHeight=1766&originWidth=1802&originalType=binary&ratio=1&rotation=0&showTitle=false&size=290072&status=done&style=none&taskId=u33a5d9d5-3b43-4310-8ecd-741d0cd00e3&title=)


### 循环
C 语言中提供了多种循环结构，即 `do-while`、`while`、`for`。
可以用条件测试和跳转组合起来实现循环的效果。
​

##### (1) `do-while` 循环
![截屏2021-12-17 16.55.47.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639731942541-03a128aa-f257-4dd5-8dbd-e55a065b8e9a.png#clientId=u3ca5926d-460e-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ub6dc155d&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-17%2016.55.47.png&originHeight=1054&originWidth=2116&originalType=binary&ratio=1&rotation=0&showTitle=false&size=958611&status=done&style=none&taskId=u51cfd0dd-5b11-4734-992c-c16fb889ab1&title=)


##### （2）`while` 循环
![截屏2021-12-17 17.28.38.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639733337513-62a14643-cf65-49b1-8d7d-2b1c81d8df51.png#clientId=u3ca5926d-460e-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ue65718b1&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-17%2017.28.38.png&originHeight=1714&originWidth=2448&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1483954&status=done&style=none&taskId=u794fe1aa-a3c6-4679-9d17-cb52a4a3c9b&title=)


##### （3）`for` 循环
![截屏2021-12-17 17.37.50.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639733881651-c210a39d-4901-45b8-a62e-fbc840d2dc40.png#clientId=u3ca5926d-460e-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u35c3d803&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-17%2017.37.50.png&originHeight=1642&originWidth=1830&originalType=binary&ratio=1&rotation=0&showTitle=false&size=946542&status=done&style=none&taskId=u8ca13d04-d3c5-4ded-b588-8616ac4e489&title=)


### switch 语句
![截屏2021-12-17 17.51.06.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639734683518-b61c2df3-88d1-4fb3-be2f-95484f936417.png#clientId=u3ca5926d-460e-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ud7e24098&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-17%2017.51.06.png&originHeight=346&originWidth=1154&originalType=binary&ratio=1&rotation=0&showTitle=false&size=600063&status=done&style=none&taskId=u3e803b45-dbd5-411d-971e-97a72470008&title=)
> 💡 特别说明
> ​

> 由于 switch 的变量 n 可以是任意整数，因此编译器经常将 n 减去某个偏移量，把取值范围移到从 0 开始，即 0 ~ 某个大于0的数之间，如下图所示，先将 n - 100，把取值范围移到 0 和 6 之间

![截屏2021-12-17 20.51.40.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639745513136-a4736765-10f7-405b-9da9-c94864d40e16.png#clientId=uca56052a-acab-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ube379d98&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-17%2020.51.40.png&originHeight=1572&originWidth=1906&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1875510&status=done&style=none&taskId=u2146f981-d0d0-49e8-b635-c5abe97c8df&title=)
#### 跳转表
![截屏2021-12-17 17.54.06.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639734940329-bcbcfa1c-9fed-41c0-b4e8-cf729c911918.png#clientId=u3ca5926d-460e-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u8dfcfbfa&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-17%2017.54.06.png&originHeight=1196&originWidth=1926&originalType=binary&ratio=1&rotation=0&showTitle=false&size=515525&status=done&style=none&taskId=u519d67c1-c6b0-4896-a923-9875d033524&title=)
#### Fall through
case 中缺失 break 语句的情况。
![截屏2021-12-17 20.55.26.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1639745735241-80c49765-e302-4df3-81df-f2ce7d2d4747.png#clientId=uca56052a-acab-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u44c3c5b2&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-17%2020.55.26.png&originHeight=1178&originWidth=1092&originalType=binary&ratio=1&rotation=0&showTitle=false&size=297686&status=done&style=none&taskId=u6d962267-3da5-46cd-8f06-55a64cb2fe7&title=)


## 过程
过程是软件中一种很重要的抽象。它提供了一种封装代码的方式，用一组指定的参数和一个可选的返回值实现了某种功能。
​

不同编程语言中，过程的形式多样：函数（function）、方法（method）、子例程（subroutine）等。
​

### 运行时栈
当过程需要的存储空间超出寄存器能够存放的大小时，就会在栈上分配空间，这部分成为过程的栈帧(stack frame)。
​

将栈指针 `%rsp` 减小一个适当的量可以为没有指定初始值的数据在栈上分配空间，类似的，可以通过增加栈指针来释放空间。
​

当过程 P 调用过程 Q 时，会把返回地址压入栈中，指明当 Q 返回时，要从 P 程序的那个位置继续执行。
​

我们把这个返回地址当做 P 的栈帧的一部分，因为它存放的是与 P 相关的状态。
​

Q 的代码会扩展当前栈的边界，分配它的栈帧所需的空间，在这个空间中，它可以 保存寄存器的值、分配局部变量空间、为他调用的过程设置参数。
​

大多数过程的栈帧都是定长的，在过程的开始就分配好了。
![截屏2021-12-23 20.10.14.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1640261425100-d92c1f32-4f22-40b8-968e-6406261821bd.png#clientId=u67fc2ff7-ad96-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u426d5821&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-23%2020.10.14.png&originHeight=1116&originWidth=684&originalType=binary&ratio=1&rotation=0&showTitle=false&size=641817&status=done&style=none&taskId=u49f84ee3-6d26-4876-880b-ad80c6bf37e&title=)


### 传递控制
![截屏2021-12-23 20.18.03.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1640261922817-e624875b-0e3b-47f2-bb39-16dcfe4d8835.png#clientId=u67fc2ff7-ad96-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u9c53e210&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-23%2020.18.03.png&originHeight=916&originWidth=1442&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1524440&status=done&style=none&taskId=ue8da7ad0-3990-4533-9937-40784f63d40&title=)
![截屏2021-12-23 20.21.56.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1640262128679-ebf699cf-d4c3-4e07-b7bf-636df9104eae.png#clientId=u67fc2ff7-ad96-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u8db5ee39&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-23%2020.21.56.png&originHeight=1234&originWidth=1476&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1219058&status=done&style=none&taskId=udb17e3f2-5dc1-4ebb-88f3-3072746bda5&title=)


### 传递数据
![截屏2021-12-23 20.24.23.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1640262285578-21e8a3a2-56a4-4d5c-9f08-a2f7190149f4.png#clientId=u67fc2ff7-ad96-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u60178dbb&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-23%2020.24.23.png&originHeight=808&originWidth=1430&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1286873&status=done&style=none&taskId=u7671afe5-e1cb-4d6f-bb3d-644b22e4693&title=)
![截屏2021-12-23 20.24.33.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1640262292242-09a15c9f-8ec3-4221-b1aa-dd987d2e4e4c.png#clientId=u67fc2ff7-ad96-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u44bf79d8&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-23%2020.24.33.png&originHeight=130&originWidth=1394&originalType=binary&ratio=1&rotation=0&showTitle=false&size=160674&status=done&style=none&taskId=ub378c624-c157-4f18-98f8-3b0794abaa6&title=)
![截屏2021-12-23 20.27.54.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1640262484320-db8b14c2-3ae0-4708-b815-9403b27ff775.png#clientId=u67fc2ff7-ad96-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u1a960831&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-23%2020.27.54.png&originHeight=768&originWidth=1462&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1016027&status=done&style=none&taskId=ud3e0c518-ae2a-46c2-9bec-08c0e518fea&title=)
### 分配和释放内存
#### 栈上的局部存储
![截屏2021-12-23 20.29.29.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1640262578445-84053069-6005-4281-9732-27909dd9e8ee.png#clientId=u67fc2ff7-ad96-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u0c387a90&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-23%2020.29.29.png&originHeight=348&originWidth=1372&originalType=binary&ratio=1&rotation=0&showTitle=false&size=542832&status=done&style=none&taskId=u7e1bc000-c871-47f7-aeb4-d3de6b61ec7&title=)
![截屏2021-12-23 20.37.25.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1640263060183-4a4fa6fc-a767-46ba-b8fd-4e14cdf8a1e0.png#clientId=u67fc2ff7-ad96-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u30b24664&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-23%2020.37.25.png&originHeight=1394&originWidth=2840&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2776565&status=done&style=none&taskId=u8de59ea5-e3a3-4940-8142-34fffe18415&title=)
#### 寄存器的局部存储
当一个过程（调用者）调用另一个过程（被调用者）时，要保证被调用者不会覆盖掉调用者稍后会使用的寄存器值。
​

##### （1）被调用者保存寄存器
寄存器 `%rbx`、`%rbp` 和 `%r12 ~ %r15` 被划分为被调用者保存寄存器。
​

当过程 P 调用过程 Q 时，Q 必须保存这些寄存器的值，保证它们的值在 Q 返回到 P 时与 Q 被调用时是一样的。
​

过程 Q 保存一个寄存器的值不变有两种方式：

1. 不去改变它
1. 把原始值压入栈中，改变寄存器的值，然后在返回前从栈中弹出旧值。

​

##### （2）调用者保存寄存器
除了 被调用者保存寄存器 和 栈指针 `%rsp`，其他的寄存器都分类为调用者保存寄存器。
​

过程 P 在某个此类寄存器中有局部数据，然后调用过程 Q，因为 Q 可以随意修改这个寄存器，所以在调用之前，首先保存好这类寄存器中的数据。
![截屏2021-12-23 20.50.07.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1640263826036-b04d2974-7234-4800-84e4-698d55751ad7.png#clientId=u67fc2ff7-ad96-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u212f22e8&margin=%5Bobject%20Object%5D&name=%E6%88%AA%E5%B1%8F2021-12-23%2020.50.07.png&originHeight=1048&originWidth=1046&originalType=binary&ratio=1&rotation=0&showTitle=false&size=841391&status=done&style=none&taskId=ueea50204-5874-405e-a30c-ea6f468baed&title=)














