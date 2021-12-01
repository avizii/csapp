## 信息存储
### bit & byte
`1 byte = 8 bit`
![1.gif](https://cdn.nlark.com/yuque/0/2021/gif/1488287/1638194799808-18049e12-1ae8-4565-98b8-abd4c0297d0f.gif#clientId=u073fa786-3f66-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u079423e0&margin=%5Bobject%20Object%5D&name=1.gif&originHeight=1000&originWidth=1978&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1475174&status=done&style=none&taskId=uf574ee75-c468-4db0-8d89-ee36031a8b5&title=)


### 进制间的转换
#### 0 ~ 15 进制表
![0-15进制表.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638194822181-88cdaf09-4448-4f73-bdf5-91e528231d97.png#clientId=u073fa786-3f66-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=uc58040dc&margin=%5Bobject%20Object%5D&name=0-15%E8%BF%9B%E5%88%B6%E8%A1%A8.png&originHeight=914&originWidth=2118&originalType=binary&ratio=1&rotation=0&showTitle=false&size=547565&status=done&style=none&taskId=udfefeae4-d8af-4150-819b-b5bbc543f6c&title=)


#### 2 进制 & 16 进制间的转换
![2.gif](https://cdn.nlark.com/yuque/0/2021/gif/1488287/1638194838924-d0bd2e21-828b-4fd5-920a-764e15a46a4d.gif#clientId=u073fa786-3f66-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u8aabce6f&margin=%5Bobject%20Object%5D&name=2.gif&originHeight=1000&originWidth=1978&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2093728&status=done&style=none&taskId=u77790d37-4e4e-4082-8025-5fc92561b07&title=)


#### 10 进制 & 16 进制间的转换
除n取余逆序排列法
![3.gif](https://cdn.nlark.com/yuque/0/2021/gif/1488287/1638194850118-decdbfe3-31e5-4e08-ad69-e4bf7166af43.gif#clientId=u073fa786-3f66-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u6e7b4ff3&margin=%5Bobject%20Object%5D&name=3.gif&originHeight=1000&originWidth=1978&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2025612&status=done&style=none&taskId=u70329d35-9eb8-4a9a-b862-5e5be49477e&title=)


### C 语言中数据类型长度
![c数据类型长度.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638194866108-de90fca8-4273-4d8f-8e2d-3c8dc997ddfe.png#clientId=u073fa786-3f66-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=udea3bf63&margin=%5Bobject%20Object%5D&name=c%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B%E9%95%BF%E5%BA%A6.png&originHeight=1076&originWidth=2058&originalType=binary&ratio=1&rotation=0&showTitle=false&size=659147&status=done&style=none&taskId=u986b03e8-b55b-41b7-9e12-2cdcf244ef8&title=)


### 数据在内存中的排布

- 大端法：最高有效字节存储在最前面
- 小端法：最低有效字节存储在最前面

![4.gif](https://cdn.nlark.com/yuque/0/2021/gif/1488287/1638194890056-e38ada27-e030-4795-aded-e8372f82f181.gif#clientId=u073fa786-3f66-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u2f1a5d7f&margin=%5Bobject%20Object%5D&name=4.gif&originHeight=1000&originWidth=1978&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1653831&status=done&style=none&taskId=u359f6350-835f-4a8c-8a34-91e6dc9a578&title=)


### 布尔运算
![布尔运算.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638194924131-482ec97b-38bb-4e24-bfcd-9c1baf0c37db.png#clientId=u073fa786-3f66-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ub5a30675&margin=%5Bobject%20Object%5D&name=%E5%B8%83%E5%B0%94%E8%BF%90%E7%AE%97.png&originHeight=972&originWidth=1870&originalType=binary&ratio=1&rotation=0&showTitle=false&size=441545&status=done&style=none&taskId=ucd77adf6-f5c9-42cd-95cb-701234983f3&title=)


### 逻辑运算
所有非 0 的参数都表示 `true`，只有参数 0(`0x00`) 表示 `false`
![逻辑运算.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638194933910-2090b1e8-1984-4207-a771-49fcd389e19b.png#clientId=u073fa786-3f66-4&crop=0&crop=0&crop=1&crop=1&from=ui&height=702&id=u68e05c1c&margin=%5Bobject%20Object%5D&name=%E9%80%BB%E8%BE%91%E8%BF%90%E7%AE%97.png&originHeight=626&originWidth=1018&originalType=binary&ratio=1&rotation=0&showTitle=false&size=97435&status=done&style=none&taskId=u582d6cb3-ef47-49de-8e69-4999cadff4f&title=&width=1141)


### 左右移操作

- 逻辑左移：丢弃高位，在低位补 `0`
- 逻辑右移：丢弃低位，在高位补 `0`
- 算术右移：丢弃低位，在高位补 `操作对象的最高位`；当操作对象的最高位为 1 时，则补 `1`，若为 0 时，则补 `0`

![5.gif](https://cdn.nlark.com/yuque/0/2021/gif/1488287/1638195009648-7e45c458-6de2-4fc6-8cd6-10b0896da583.gif#clientId=u073fa786-3f66-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=uab3b7cd3&margin=%5Bobject%20Object%5D&name=5.gif&originHeight=1000&originWidth=1978&originalType=binary&ratio=1&rotation=0&showTitle=false&size=3253027&status=done&style=none&taskId=u40dc6e8b-ccaa-4fbc-91f8-3b7a688270e&title=)


## 整数表示
### 整数数据类型
![C中整数数据类型.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638276231225-f026a05e-7e05-44fa-8dba-a377eaf8f85f.png#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=uf26c1116&margin=%5Bobject%20Object%5D&name=C%E4%B8%AD%E6%95%B4%E6%95%B0%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B.png&originHeight=1094&originWidth=2054&originalType=binary&ratio=1&rotation=0&showTitle=false&size=632983&status=done&style=none&taskId=u6d723485-788c-4083-95d8-e532368bbda&title=)


### 无符号数编码(unsigned)
![无符号数编码表示.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638276243610-57476a2b-9dbf-405e-ad2b-d3eae0ed295c.png#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u2d156ec1&margin=%5Bobject%20Object%5D&name=%E6%97%A0%E7%AC%A6%E5%8F%B7%E6%95%B0%E7%BC%96%E7%A0%81%E8%A1%A8%E7%A4%BA.png&originHeight=868&originWidth=2060&originalType=binary&ratio=1&rotation=0&showTitle=false&size=512086&status=done&style=none&taskId=ue4897ff9-db06-4eef-9a61-b8a2005e7ab&title=) 
#### 无符号数的最大值 Umax
所有的二进制位全为 1 时，表示最大
![Screen Shot 2021-11-30 at 20.55.14.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638277039207-91de6958-725f-4830-853d-f298add84826.png#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ua140351f&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-11-30%20at%2020.55.14.png&originHeight=968&originWidth=1960&originalType=binary&ratio=1&rotation=0&showTitle=false&size=410094&status=done&style=none&taskId=ufb4ac8ba-d0d1-4163-9aed-364e5972a2f&title=)




### 有符号数编码(补码)
最高位为符号位，记为负数
![有符号数编码表示.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638276259588-7422aff8-7ea1-48e4-bd07-ea8108fffa58.png#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u0c1abdef&margin=%5Bobject%20Object%5D&name=%E6%9C%89%E7%AC%A6%E5%8F%B7%E6%95%B0%E7%BC%96%E7%A0%81%E8%A1%A8%E7%A4%BA.png&originHeight=772&originWidth=2024&originalType=binary&ratio=1&rotation=0&showTitle=false&size=409239&status=done&style=none&taskId=ue0bac085-a91f-45aa-b9d3-9436e9b6eb8&title=)
#### 有符号数的最小值 Tmin
二进制位中，最高位为 1，其余位为 0 时，表示最小
![Screen Shot 2021-11-30 at 20.56.15.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638277104120-5243c05a-62d2-4dd2-bb22-354bef63e783.png#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u1b03ff18&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-11-30%20at%2020.56.15.png&originHeight=968&originWidth=1918&originalType=binary&ratio=1&rotation=0&showTitle=false&size=469045&status=done&style=none&taskId=u270c580b-6994-4c42-887a-65d8a2da1c5&title=)
#### 有符号数的最大值 Tmax
二进制位中，最高位符号位为 0，其余位为 1 时，表示最大
![image.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638277087718-9769731a-aa75-4328-b2d7-1db8e783a0fe.png#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u880f40c9&margin=%5Bobject%20Object%5D&name=image.png&originHeight=970&originWidth=1922&originalType=binary&ratio=1&rotation=0&showTitle=false&size=311106&status=done&style=none&taskId=u5b22fbfc-c4f0-4df9-840d-f3d22e11258&title=)
#### 特殊数值 -1
所有的二进制位全为 1 时，表示 -1
![Screen Shot 2021-11-30 at 20.56.43.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638277252835-a75d46d4-8150-4f37-80ad-1f1081561363.png#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ub9fa7980&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-11-30%20at%2020.56.43.png&originHeight=622&originWidth=1938&originalType=binary&ratio=1&rotation=0&showTitle=false&size=356953&status=done&style=none&taskId=uc9f11e1a-b980-44f1-99cf-edb7a6299ad&title=)


### 无符号数与有符号数间的转换
二进制的位模式不变，只是位的解释方式变化
![无符号数与有符号数间的转换.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638277368515-4a42fb04-bb45-4ae7-94a2-b8aa6339e72c.png#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u2d47510e&margin=%5Bobject%20Object%5D&name=%E6%97%A0%E7%AC%A6%E5%8F%B7%E6%95%B0%E4%B8%8E%E6%9C%89%E7%AC%A6%E5%8F%B7%E6%95%B0%E9%97%B4%E7%9A%84%E8%BD%AC%E6%8D%A2.png&originHeight=782&originWidth=2144&originalType=binary&ratio=1&rotation=0&showTitle=false&size=503711&status=done&style=none&taskId=u6f315dd6-6bc6-4383-8af8-7d1fe1275de&title=)


#### 有符号数 -> 无符号数
![Screen Shot 2021-11-30 at 21.04.33.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638277499941-dfad9f12-7da8-4289-922a-873131fb9c33.png#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u55cf479d&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-11-30%20at%2021.04.33.png&originHeight=546&originWidth=1618&originalType=binary&ratio=1&rotation=0&showTitle=false&size=93353&status=done&style=none&taskId=udb87ba2d-9555-47ab-b320-fa55372b57b&title=)
#### 无符号数 -> 有符号数
![Screen Shot 2021-11-30 at 21.04.44.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638277529044-f425f90e-69ef-4c83-b22e-422886d69223.png#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u88b1559c&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-11-30%20at%2021.04.44.png&originHeight=538&originWidth=1756&originalType=binary&ratio=1&rotation=0&showTitle=false&size=98293&status=done&style=none&taskId=u40851a48-1591-4dae-99d2-58eb3b64efa&title=)


### 不同字长的整数之间的转换
#### 扩展：换成更大的数据类型
##### 无符号数：零扩展
![零扩展.gif](https://cdn.nlark.com/yuque/0/2021/gif/1488287/1638278377328-ef75ac86-4a7c-47c6-8d68-f32833049e13.gif#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u1c36da9b&margin=%5Bobject%20Object%5D&name=%E9%9B%B6%E6%89%A9%E5%B1%95.gif&originHeight=1000&originWidth=1978&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1775852&status=done&style=none&taskId=u0a8e9c4a-92c5-4d41-9878-5f3786e768a&title=)


##### 有符号数：符号位扩展
![符号位扩展.gif](https://cdn.nlark.com/yuque/0/2021/gif/1488287/1638278664288-8e97c7c5-2d0b-4d44-99c6-9f9fce813a02.gif#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u9175ed98&margin=%5Bobject%20Object%5D&name=%E7%AC%A6%E5%8F%B7%E4%BD%8D%E6%89%A9%E5%B1%95.gif&originHeight=1000&originWidth=1978&originalType=binary&ratio=1&rotation=0&showTitle=false&size=4073774&status=done&style=none&taskId=ub29e3f1a-f12c-49d6-9d89-f9205fd1b64&title=)


符号位扩展证明：
![符号位扩展证明.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638278450029-e5bd23f6-b71b-4bab-9d51-7ce321e52fa2.png#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=uefa29e4c&margin=%5Bobject%20Object%5D&name=%E7%AC%A6%E5%8F%B7%E4%BD%8D%E6%89%A9%E5%B1%95%E8%AF%81%E6%98%8E.png&originHeight=854&originWidth=2108&originalType=binary&ratio=1&rotation=0&showTitle=false&size=551047&status=done&style=none&taskId=u65b8a1a0-c1b8-4be4-b521-651e9b812ad&title=)


#### 截断：换成更小的数据类型
##### 无符号数：x有2k位，丢弃高k位，剩余低k位，相当于取模 mod 2k
![无符号数截取.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638278414780-24181968-c4a9-4d74-940a-da66d385a4a9.png#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u328c342c&margin=%5Bobject%20Object%5D&name=%E6%97%A0%E7%AC%A6%E5%8F%B7%E6%95%B0%E6%88%AA%E5%8F%96.png&originHeight=518&originWidth=2204&originalType=binary&ratio=1&rotation=0&showTitle=false&size=418722&status=done&style=none&taskId=u036287b5-1e1a-454f-9072-f304a7df425&title=)
##### 有符号数：先转为无符号数，取模(丢弃高k位，剩余低k位)，再转回有符号数
![有符号数截取.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638278426661-176cad8c-fe9d-4895-bba3-4f553a8b7e1f.png#clientId=u4fdbd714-cc9d-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u1c8152e1&margin=%5Bobject%20Object%5D&name=%E6%9C%89%E7%AC%A6%E5%8F%B7%E6%95%B0%E6%88%AA%E5%8F%96.png&originHeight=620&originWidth=2244&originalType=binary&ratio=1&rotation=0&showTitle=false&size=463693&status=done&style=none&taskId=uf422a27e-06ce-4747-bd3e-29935fd3f70&title=)
## 整数运算






## 浮点数


## ​

