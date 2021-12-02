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
### 加法
#### 无符号数
![无符号数加法.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638365562718-8b56f761-ef4d-498a-b6c7-69b534dee0f3.png#clientId=uac42b9d8-2a1a-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u34141786&margin=%5Bobject%20Object%5D&name=%E6%97%A0%E7%AC%A6%E5%8F%B7%E6%95%B0%E5%8A%A0%E6%B3%95.png&originHeight=716&originWidth=2066&originalType=binary&ratio=1&rotation=0&showTitle=false&size=249918&status=done&style=none&taskId=u267aac0e-236c-409e-bbd6-11eab5acdfb&title=)
溢出：
![Screen Shot 2021-12-01 at 21.34.42.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638365713982-3c861562-9729-45f3-801a-ad0c02ad3c22.png#clientId=uac42b9d8-2a1a-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u7b13037a&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-01%20at%2021.34.42.png&originHeight=534&originWidth=1598&originalType=binary&ratio=1&rotation=0&showTitle=false&size=73433&status=done&style=none&taskId=u8a3333bb-5cc8-4634-b6c8-f744098c8d7&title=)
​

#### 有符号数
![有符号数加法.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638365625338-952b1f58-9383-444a-bed5-cc5aae7cb9e6.png#clientId=uac42b9d8-2a1a-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u20c3c2b6&margin=%5Bobject%20Object%5D&name=%E6%9C%89%E7%AC%A6%E5%8F%B7%E6%95%B0%E5%8A%A0%E6%B3%95.png&originHeight=680&originWidth=2138&originalType=binary&ratio=1&rotation=0&showTitle=false&size=391832&status=done&style=none&taskId=uf361ae4e-a04d-4e41-8653-8ad48c802fe&title=)
溢出：

- 正溢出
- 负溢出

![Screen Shot 2021-12-01 at 21.35.04.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638365721126-2028ecef-64e7-4911-baa5-fc79fe9234f9.png#clientId=uac42b9d8-2a1a-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u357616b5&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-01%20at%2021.35.04.png&originHeight=684&originWidth=1526&originalType=binary&ratio=1&rotation=0&showTitle=false&size=136036&status=done&style=none&taskId=u9ba9d20d-c1f6-44d5-858e-265fb615b14&title=)


### 减法 - 加法逆元
#### 无符号数
![无符号数减法-加法逆元.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638365771082-8b96806f-c1a5-42de-8df4-d51f8c504afe.png#clientId=uac42b9d8-2a1a-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u07465833&margin=%5Bobject%20Object%5D&name=%E6%97%A0%E7%AC%A6%E5%8F%B7%E6%95%B0%E5%87%8F%E6%B3%95-%E5%8A%A0%E6%B3%95%E9%80%86%E5%85%83.png&originHeight=762&originWidth=2212&originalType=binary&ratio=1&rotation=0&showTitle=false&size=291703&status=done&style=none&taskId=ue0ef25e4-273b-4a1d-bf38-e3db402b224&title=)
#### 有符号数
![有符号数减法-加法逆元.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638365838003-277cd330-cd69-4099-8c0b-46f7ce996bf6.png#clientId=uac42b9d8-2a1a-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=uf5eaf268&margin=%5Bobject%20Object%5D&name=%E6%9C%89%E7%AC%A6%E5%8F%B7%E6%95%B0%E5%87%8F%E6%B3%95-%E5%8A%A0%E6%B3%95%E9%80%86%E5%85%83.png&originHeight=932&originWidth=2052&originalType=binary&ratio=1&rotation=0&showTitle=false&size=362565&status=done&style=none&taskId=u781cbe0a-3774-4aee-a0a4-e358fe4d24e&title=)
#### 有符号数非 `-x` 的位级表示

- 对每一位求补，再对结果加1
- 将位向量分为两部分，假设k是最右边的1的位置，对位k左边的所有位取反
```json
假设 x = 10100101, 则：

方式1：
-x = ~x + 1 = 01011010 + 00000001 = 01011011

方式2:
-x = 0101101 1
```


### 乘法
#### 无符号数
溢出截断，相当于取模 mod 2k
![无符号数乘法截取.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638366091424-2a0cfa91-e8b1-499c-b4f4-3ee08fe1952d.png#clientId=uac42b9d8-2a1a-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u2867e909&margin=%5Bobject%20Object%5D&name=%E6%97%A0%E7%AC%A6%E5%8F%B7%E6%95%B0%E4%B9%98%E6%B3%95%E6%88%AA%E5%8F%96.png&originHeight=892&originWidth=2136&originalType=binary&ratio=1&rotation=0&showTitle=false&size=304821&status=done&style=none&taskId=u16e7aa13-8f05-4f0c-a996-524476a4692&title=)
#### 有符号数
转换成无符号数 -> 截断取模 -> 转换成有符号数
![有符号数乘法截取.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638366184537-b7b11796-48fe-41a0-8b1b-d966cd529fdb.png#clientId=uac42b9d8-2a1a-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u9d999e2f&margin=%5Bobject%20Object%5D&name=%E6%9C%89%E7%AC%A6%E5%8F%B7%E6%95%B0%E4%B9%98%E6%B3%95%E6%88%AA%E5%8F%96.png&originHeight=934&originWidth=2230&originalType=binary&ratio=1&rotation=0&showTitle=false&size=338122&status=done&style=none&taskId=u2c70951b-0cf1-4005-8c24-dff6fd6a664&title=)
#### 用左移和加减法运算的组合来代替乘以常量因子的乘法

- 原因：乘法运算所需的时钟周期大

![左移和加减法运算组合.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638366249809-e50e68e1-bb9e-4abb-a7dc-1a7494f66c9f.png#clientId=uac42b9d8-2a1a-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ua1d479cf&margin=%5Bobject%20Object%5D&name=%E5%B7%A6%E7%A7%BB%E5%92%8C%E5%8A%A0%E5%87%8F%E6%B3%95%E8%BF%90%E7%AE%97%E7%BB%84%E5%90%88.png&originHeight=962&originWidth=2104&originalType=binary&ratio=1&rotation=0&showTitle=false&size=355203&status=done&style=none&taskId=u5056f07d-ca9d-4023-8447-71078a4f743&title=)

- 组合公式：

![Screen Shot 2021-12-01 at 21.48.03.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638366519003-86868282-e683-4541-a8d2-c186476ee22e.png#clientId=uac42b9d8-2a1a-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ub63ea421&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-01%20at%2021.48.03.png&originHeight=988&originWidth=2560&originalType=binary&ratio=1&rotation=0&showTitle=false&size=2257366&status=done&style=none&taskId=ud238f1b8-bc3f-445c-a5f5-c3fb1ca5ffc&title=)
### 除法 - 除以2的幂
整数的除法中，除以2的幂也可以用移位运算来实现，使用的是右移运算。
整数的除法总是向0舍入。
​

#### 无符号数

- 逻辑右移

![Screen Shot 2021-12-01 at 21.55.47.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638366960064-fd8a2a94-93e7-4a47-becc-2d5420f49c7f.png#clientId=uac42b9d8-2a1a-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=uadde584a&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-01%20at%2021.55.47.png&originHeight=150&originWidth=1870&originalType=binary&ratio=1&rotation=0&showTitle=false&size=233427&status=done&style=none&taskId=ub7d0775d-50e3-49a8-9193-ad0a86c70a7&title=)
​

#### 有符号数

- 算术右移

![Screen Shot 2021-12-01 at 21.58.13.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638367098392-35c98edb-48a8-45e7-b222-19d43b121629.png#clientId=uac42b9d8-2a1a-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u690553a2&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-01%20at%2021.58.13.png&originHeight=210&originWidth=1952&originalType=binary&ratio=1&rotation=0&showTitle=false&size=321318&status=done&style=none&taskId=uc4190208-80da-4210-a3d5-de9f5348130&title=)
对于非负数的补码来说，向下舍入是没有问题的；但是对于负数而言，向下舍入并不是向0舍入，我们可以通过在移位前偏置这个值，来修正这种不合适的舍入。
![Screen Shot 2021-12-01 at 22.02.51.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638406615954-c60a37e5-8e57-4d43-bb20-f0716d8dc4ed.png#clientId=u3021479d-a2a9-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u968d13ec&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-01%20at%2022.02.51.png&originHeight=280&originWidth=1940&originalType=binary&ratio=1&rotation=0&showTitle=false&size=552754&status=done&style=none&taskId=u5b94dfd0-8163-4f25-9bdf-7036734100b&title=)
![Screen Shot 2021-12-01 at 22.03.00.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638367393051-25f2c535-c341-4294-9e25-7ea40d0f0482.png#clientId=uac42b9d8-2a1a-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ud306f793&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-01%20at%2022.03.00.png&originHeight=86&originWidth=1652&originalType=binary&ratio=1&rotation=0&showTitle=false&size=137918&status=done&style=none&taskId=u693692cf-9acb-4248-8457-1f38c069e5d&title=)


## 浮点数
### 二进制小数
![带小数点的二进制.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638452459395-ca4136ec-f17c-4cc7-814a-23f34b99bec0.png#clientId=u58308c6c-3f42-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u83f1b580&margin=%5Bobject%20Object%5D&name=%E5%B8%A6%E5%B0%8F%E6%95%B0%E7%82%B9%E7%9A%84%E4%BA%8C%E8%BF%9B%E5%88%B6.png&originHeight=1050&originWidth=2086&originalType=binary&ratio=1&rotation=0&showTitle=false&size=258426&status=done&style=none&taskId=uc9def2e2-c469-4ffb-be69-02ff8ba6ac1&title=)
### IEEE浮点表示
![IEEE浮点数表示.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638452477129-0f3a1beb-6374-47ca-b968-2c2d727bf035.png#clientId=u58308c6c-3f42-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u58d8cdde&margin=%5Bobject%20Object%5D&name=IEEE%E6%B5%AE%E7%82%B9%E6%95%B0%E8%A1%A8%E7%A4%BA.png&originHeight=948&originWidth=1908&originalType=binary&ratio=1&rotation=0&showTitle=false&size=362296&status=done&style=none&taskId=ueba1c081-7c44-4cc8-afe9-2cce56c6d54&title=)
![IEEE浮点数表示2.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638452489680-75d74b84-2c9c-4d16-9f62-9e09a28ad2d2.png#clientId=u58308c6c-3f42-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u76ee8bb0&margin=%5Bobject%20Object%5D&name=IEEE%E6%B5%AE%E7%82%B9%E6%95%B0%E8%A1%A8%E7%A4%BA2.png&originHeight=554&originWidth=1460&originalType=binary&ratio=1&rotation=0&showTitle=false&size=901468&status=done&style=none&taskId=u129097bb-38fc-42e4-a4a5-0e55abe0e15&title=)
### IEEE浮点的数值类型
![image.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638452633840-6622fe9b-93e9-4a53-9004-3eae2a7a9c54.png#clientId=u58308c6c-3f42-4&crop=0&crop=0&crop=1&crop=1&from=drop&id=u44a4f17d&margin=%5Bobject%20Object%5D&name=image.png&originHeight=944&originWidth=2052&originalType=binary&ratio=1&rotation=0&showTitle=false&size=271296&status=done&style=none&taskId=udc576fd7-bacc-49f5-828b-fbe256bdf3c&title=)
![Screen Shot 2021-12-02 at 21.48.58.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638452960865-5c1eede9-b5bc-43f7-aea7-31061808a848.png#clientId=u58308c6c-3f42-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ubbeac8d1&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-02%20at%2021.48.58.png&originHeight=1118&originWidth=1476&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1358207&status=done&style=none&taskId=uf52d2307-3e5c-49a9-b260-4a6fae2ffda&title=)


#### 规格化

- `bias = 2^(k-1) - 1`
- `E = exp - bias`
- `M = 1 + f`

![规格化1.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638452656107-6e79ba1e-0742-4193-a65b-7d638581dc6e.png#clientId=u58308c6c-3f42-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u52e27137&margin=%5Bobject%20Object%5D&name=%E8%A7%84%E6%A0%BC%E5%8C%961.png&originHeight=884&originWidth=2138&originalType=binary&ratio=1&rotation=0&showTitle=false&size=486418&status=done&style=none&taskId=ue2b9c137-7495-41dd-b9f3-15f53422854&title=)
![规格化2.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638452707553-c85e5ede-6206-4747-b7d4-d465560e6552.png#clientId=u58308c6c-3f42-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=uf107aa04&margin=%5Bobject%20Object%5D&name=%E8%A7%84%E6%A0%BC%E5%8C%962.png&originHeight=952&originWidth=2002&originalType=binary&ratio=1&rotation=0&showTitle=false&size=405759&status=done&style=none&taskId=u9ef8afe5-fde7-45c1-840f-a8dab26c2d0&title=)
​

实例：
![特殊值实例.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638453050887-0e2c2e8b-1e56-46e1-827f-3166e9d927ac.png#clientId=uddd52223-08b0-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=udf170f4d&margin=%5Bobject%20Object%5D&name=%E7%89%B9%E6%AE%8A%E5%80%BC%E5%AE%9E%E4%BE%8B.png&originHeight=962&originWidth=2086&originalType=binary&ratio=1&rotation=0&showTitle=false&size=512975&status=done&style=none&taskId=uca8f039d-2833-4bcd-aea3-c8ece201024&title=)
#### 
#### 非规格化

- `E = 1 - bias`
- `M = f`

![非规格化.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638452854740-17ff0f67-261d-48cd-87af-299242fb414a.png#clientId=u58308c6c-3f42-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u568c9e76&margin=%5Bobject%20Object%5D&name=%E9%9D%9E%E8%A7%84%E6%A0%BC%E5%8C%96.png&originHeight=878&originWidth=2076&originalType=binary&ratio=1&rotation=0&showTitle=false&size=407020&status=done&style=none&taskId=u15848e2f-8399-4422-a5e0-ba0148b6c07&title=)


实例：
![非规格化实例.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638452862069-cdf6573d-7cd5-44fe-8c79-95e7ade91cb5.png#clientId=u58308c6c-3f42-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u1cb9cd2a&margin=%5Bobject%20Object%5D&name=%E9%9D%9E%E8%A7%84%E6%A0%BC%E5%8C%96%E5%AE%9E%E4%BE%8B.png&originHeight=980&originWidth=2112&originalType=binary&ratio=1&rotation=0&showTitle=false&size=665887&status=done&style=none&taskId=u73d2c605-12b8-4877-b21b-fbe85afb3a4&title=)
#### 特殊值
![特殊值.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638452903015-df9184fe-9713-4518-b118-12cdf1033159.png#clientId=u58308c6c-3f42-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u77d933e4&margin=%5Bobject%20Object%5D&name=%E7%89%B9%E6%AE%8A%E5%80%BC.png&originHeight=962&originWidth=2058&originalType=binary&ratio=1&rotation=0&showTitle=false&size=453812&status=done&style=none&taskId=u3e900862-5a5a-4ec9-be3d-bdf3f21e99c&title=)


实例：
![规格化实例.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638453037623-38dbc796-c23a-41d1-ac9c-d9154d0b8b48.png#clientId=uddd52223-08b0-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u3eb41b63&margin=%5Bobject%20Object%5D&name=%E8%A7%84%E6%A0%BC%E5%8C%96%E5%AE%9E%E4%BE%8B.png&originHeight=970&originWidth=2096&originalType=binary&ratio=1&rotation=0&showTitle=false&size=561676&status=done&style=none&taskId=u6288aa15-69df-4d1b-8e2e-054565c0545&title=)


### Int 转 Float 实例
![Screen Shot 2021-12-02 at 21.52.36.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638454975288-3b9c72ba-da2c-4557-8c80-76217a658140.png#clientId=ucdd6b408-d80c-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=uc56ee5d0&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-02%20at%2021.52.36.png&originHeight=842&originWidth=1864&originalType=binary&ratio=1&rotation=0&showTitle=false&size=459457&status=done&style=none&taskId=ud839519f-91b7-4344-9d93-09b28b824bb&title=)


### 舍入
对于值x，可能无法用浮点形式来精确的表示，因此我们希望可以找到“最接近的值 x’ 来代替x，这就是舍入操作的任务。


- 向上舍入：朝大的方向舍入
- 向下舍入：朝小的方向舍入
- 向0舍入：整数向下舍入，负数向上舍入
- 向偶数舍入：向最近的值舍入

![Screen Shot 2021-12-02 at 21.54.09.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638454999677-391c0a13-5422-4ee7-bc82-8f626491f18b.png#clientId=ucdd6b408-d80c-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u19eb5f57&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-02%20at%2021.54.09.png&originHeight=922&originWidth=1514&originalType=binary&ratio=1&rotation=0&showTitle=false&size=365328&status=done&style=none&taskId=udd79b407-374d-4056-bc4b-37ca4bcc282&title=)
#### 向偶数舍入
舍入后的最低有效数字为偶数，若是偶数则保留，若为奇数则进位  ==>  四舍六入五成双
​

对于二进制来说，最低有效数字为0则表示偶数，为1表示奇数。
​

二进制小数表示在两个可能的结果正中间的值的格式如下：
![Screen Shot 2021-12-02 at 22.17.37.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638455303987-021993a2-5749-4baf-a533-1ae067f2b08d.png#clientId=ucdd6b408-d80c-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=u906823a3&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-02%20at%2022.17.37.png&originHeight=550&originWidth=1618&originalType=binary&ratio=1&rotation=0&showTitle=false&size=1008735&status=done&style=none&taskId=ubc548dbc-ff8c-4dd5-a145-bd0d6077e6e&title=)
实例：
![Screen Shot 2021-12-02 at 22.01.53.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638455008773-e6ab0332-b877-4352-b532-338da07cd8b0.png#clientId=ucdd6b408-d80c-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=ua247dcb5&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-02%20at%2022.01.53.png&originHeight=952&originWidth=1834&originalType=binary&ratio=1&rotation=0&showTitle=false&size=472897&status=done&style=none&taskId=uffad732d-f765-40f3-aca4-93e07352ac3&title=)


### IEEE浮点的运算规则

- 不满足加法结合律
- 不满足乘法结合律
- 乘法在加法上不满足分配律

![Screen Shot 2021-12-02 at 22.31.51.png](https://cdn.nlark.com/yuque/0/2021/png/1488287/1638455527268-7a277e0c-40e3-4e18-afc3-e926fba87442.png#clientId=ucdd6b408-d80c-4&crop=0&crop=0&crop=1&crop=1&from=ui&id=uf2856784&margin=%5Bobject%20Object%5D&name=Screen%20Shot%202021-12-02%20at%2022.31.51.png&originHeight=866&originWidth=1868&originalType=binary&ratio=1&rotation=0&showTitle=false&size=525031&status=done&style=none&taskId=uec45780d-da83-4390-ac1b-fad2d8310eb&title=)


### C语言整数与浮点数的强制转换

- int -> float: 不会溢出，可舍入
- int / float -> double：不会溢出，不会舍入
- double -> float：可溢出，可舍入
- float / double -> int：可溢出，可舍入
