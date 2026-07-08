###### SAP的CO模块，代码CKM3的业务流转是怎样的？ 关注问题 写回

![image 1](<SAPCO-CKM3取值逻辑_images/imageFile1.png>)

被浏览

关注者

思爱普 (SAP) ERP 咨询 SAP ⼊⻔

匿名⽤户

3

### 1,01

# SAP的CO模块，代码CKM3的业务流转是怎样的？

创 建 时 间 ：2020-03-10 14:46:47 最 后 编 辑：2020-03-10 14:46:47

公司上线SAP,各种上线问题待解决，我负责CO核算 ，想知道实际成本的业务流转 是如何的

显示全部

关注问题 写回答 邀请回答 好问题 添加评论

分享

查看全部 2 个回答

![image 2](<SAPCO-CKM3取值逻辑_images/imageFile2.png>)

###### ERP讲堂

关注 交流可➕ :TOPSAP8

发布于 2025-01-09 19:01・四川

CKM3N取值分析

- 1. 总体思路 需要通过后台底层数据找出来ckm3n中每个数据值的来源
- 2. 逻辑思路
- 3. CKMLHD根据物料和⼯⼚查到对应的成本估算号。
- 4. 根据成本估算号和⽉份在MLDOC找到要查物料的所属当⽉数据。
- 5. 在MLDO CS中按照业务类型筛选，期初的就是AB 收据的就是ZU 消耗的就是 VN 以此类推 。
- 6. 把MLDOC中拿到得数据 对应的凭证参考到 MLDO CS 关联拿到字段 ELEMENT 组件对应的 字段TOT值可以
- 7. 根据各个组件的⾦额/MLDOC ⾥⾯实际的收据或消耗的数量就可以得到这个物料当⽉的收发实际 单位成本。


说明：直接⽤底表CKMLPRKEPH 的单位实际成本和单位标准成本只保留了两位⼩数，会导致数量 过⼤的时候；*数量差异过⼤。

三、数据来源字段具体分析

- 1. 查询ckm3n 物料 190169 公司1 0

![image 3](<SAPCO-CKM3取值逻辑_images/imageFile3.png>)

- 2、CKMLHD通过物料号 190169和⼯⼚1 0取值出成本估算编号 0101521509


赞同 添加评论 2 喜欢 分享 收起

![image 4](<SAPCO-CKM3取值逻辑_images/imageFile4.png>)

SAP的CO模块，代码CKM3的业务流转是怎样的？

![image 5](<SAPCO-CKM3取值逻辑_images/imageFile5.png>)

1. 根据成本估算号去关联MLDOC底表，并且通过年份/期间过滤出来，属于202403⽉的数据

![image 6](<SAPCO-CKM3取值逻辑_images/imageFile6.png>)

![image 7](<SAPCO-CKM3取值逻辑_images/imageFile7.png>)

![image 8](<SAPCO-CKM3取值逻辑_images/imageFile8.png>)

SAP的CO模块，代码CKM3的业务流转是怎样的？

![image 9](<SAPCO-CKM3取值逻辑_images/imageFile9.png>)

![image 10](<SAPCO-CKM3取值逻辑_images/imageFile10.png>)

![image 11](<SAPCO-CKM3取值逻辑_images/imageFile11.png>)

1. 再根据 MLDOC ⽂件参考关联到表 MLDO CS 就可以得到按照组件的实际成本 ；在 MLDO CS中按照业务类型筛选，期初的就是AB 收据的就是ZU 消耗的就是 VN ；期末库存数 量=期初库存数量+收货数量-消耗数量

![image 12](<SAPCO-CKM3取值逻辑_images/imageFile12.png>)

SAP的CO模块，代码CKM3的业务流转是怎样的？

![image 13](<SAPCO-CKM3取值逻辑_images/imageFile13.png>)

![image 14](<SAPCO-CKM3取值逻辑_images/imageFile14.png>)

1. 分析ckm3n中的 收据各个取值

- 4.1 Ckm3n中的数量


![image 15](<SAPCO-CKM3取值逻辑_images/imageFile15.png>)

⾸先在MLDOC中类型中过滤ZU 收据的

![image 16](<SAPCO-CKM3取值逻辑_images/imageFile16.png>)

###### SAP的CO模块，代码CKM3的业务流转是怎样的？

![image 17](<SAPCO-CKM3取值逻辑_images/imageFile17.png>)

#### 下载知乎客户端

与世界分享知识、经验和⻅解

查询ZU收据中MLDOC对应的字段数量，合计是1504和ckm3n是⼀致的

![image 18](<SAPCO-CKM3取值逻辑_images/imageFile18.png>)

关于作者

![image 19](<SAPCO-CKM3取值逻辑_images/imageFile19.png>)

## ERP讲堂

交流可➕ :TOPSAP8

⽂章

关注者

回答

52

56

### 3,90

关注他 发私信

被收藏 1次

料差分析 0 ⼈关注 忍冬 创建

- 4.2 查询初级评估⾦额，查询ZU收据中MLDOC对应的字段初级评估⾦额字段，合计是14154.61 和ckm3n是⼀致的


![image 20](<SAPCO-CKM3取值逻辑_images/imageFile20.png>)

相关问题

SAP启⽤sit在途⽅案后，⼯单跨⽉结算 对物料账的影响如何解决？ 4 个回答

为什么选择 SAP 会成为⾯向中⼩型企业 的解决⽅案？ 1 个回答

解读SAP Hybris系统为何获国内B2B⽤ 户⻘睐？ 2 个回答

SAP中如何将物料号扩充到其他⼯⼚？ 5 个回答

⼤家都在搜 换 换

![image 21](<SAPCO-CKM3取值逻辑_images/imageFile21.png>)

查询收据的实际值

SAP的CO模块，代码CKM3的业务流转是怎样的？

![image 22](<SAPCO-CKM3取值逻辑_images/imageFile22.png>)

把MLDOC中zu收据对应的凭证参考 放⼊MLDO CS中

![image 23](<SAPCO-CKM3取值逻辑_images/imageFile23.png>)

![image 24](<SAPCO-CKM3取值逻辑_images/imageFile24.png>)

在MLDO CS中总值字段得到实际值和CKM3N中⼀致

- 4.3 查询：ckm3n“价格”； 实际值/数量 =14154.61/1504=94.187


- 4.4 查询ckm3n中 原材料⾦额


MLDO CS中字段 Comp选择10的是原材料，和ckm3n数据⼀致

其他组件⼀样，组件类别可以再TCKH3表中查询,然后再MLDO CS中选择对应类型取数据就可 以了，就能把各个组件的值取值出来

SAP的CO模块，代码CKM3的业务流转是怎样的？

发布于 2025-01-09 19:01・四川

更多回答

查看全部 2 个回答

