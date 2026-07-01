# 信息安全工程师（第二版）章九：VPN 技术原理与应用

## 一、VPN 概述

**概念** ：（Virtual Private Network，**虚拟专用网** ）基本技术原理是把需要经过公共网传递的报文**加密处理**
后，再由公共网络发送到目的地。利用 VPN 技术能够**在不可信任的公共网络上构建一条专用的安全通道** ，经 VPN
传输的数据在公共网上具有**保密性** 。

**VPN 安全功能** ：

  * 保密性服务（Confidentiality）
  * 完整性服务（Integrity）
  * 认证服务（Authentication）

**VPN 技术风险** ：

  * VPN 产品代码实现的安全缺陷（HeartBleed）
  * VPN 密码算法安全缺陷
  * VPN 管理不当引发的安全缺陷

## 二、VPN 类型和实现技术

### 2-1 VPN 类型

  * 链路层 VPN：ATM、Frame Relay、MPLS
  * 网络层 VPN：路由过滤、隧道技术
  * 传输层 VPN：SSL

### 2-2 密码算法

  * 国外：DES、AES、RSA
  * 国内：SM1、SM3、SM4

### 2-3 密钥管理

  * SKIP（互联网简单密钥管理协议）
  * ISAKMP/Oakley（互联网安全联盟和密钥管理协议）

### 2-4 IPSec

IPSec（Internet Protocol Security）是通过对 IP 协议的分组进行加密和认证来保护 IP 协议的**网络传输协议簇** 。

  * AH：提供完整性和数据源认证，防止重放攻击
  * ESP：提供保密性服务

![](https://pic2.zhimg.com/v2-a86a10bd5a44994b6dddc0975d737e85_b.jpg)![](data:image/svg+xml;utf8,<svg
xmlns='http://www.w3.org/2000/svg' width='781' height='838'></svg>)

### 2-5 SSL

SSL（Secure Socket Layer）：传输层安全协议。

  * 传输层：SSL 记录协议
  * 应用层：SSL 握手协议（握手协议、密码规格变更协议、报警协议）

提供三种安全通信服务：

  1. 保密性通信
  2. 点对点之间的身份认证
  3. 可靠性通信

### 2-6 PPTP & L2TP

![](https://pic3.zhimg.com/v2-546179bc4b2d6326b29c573876bf11ee_b.jpg)![](data:image/svg+xml;utf8,<svg
xmlns='http://www.w3.org/2000/svg' width='906' height='858'></svg>)

## 三、VPN 主要产品与技术指标

### 3-1 VPN 主要产品

产品：IPSec VPN 网关、SSL VPN 网关，集成 IPSec、SSL 安全功能的防火墙和路由器。

  * IPSec VPN：隧道模式（主机-网关）和传输模式（主机-主机）
  * SSL VPN：C/S、网关-网关

### 3-2 VPN 产品主要技术指标

依据：**《IPSec VPN 技术规范》《SSL VPN 技术规范》**

**1。密码算法要求：**

**IPSec VPN：**

  * 非对称密码算法使用 1024 比特 RSA 或 256 比特 SM2 椭圆曲线密码算法
  * 对称密码使用 128 比特 分组的 SM1 分组密码算法，工作模式 CBC
  * 杂凑算法使用 SHA-1 或输出为 256 比特的 SM3

**SSL VPN：**

  * 非对称密码算法包括 256位 ECC椭圆曲线密码算法 SM2、IBC 标识密码算法 SM9 和1024 位以上 RSA 算法
  * 分组密码算法为 SM1 算法，工作模式 CBC
  * 杂凑算法包括 SM3 算法和 SHA-1 算法

**2。VPN 产品功能要求：**

  * **IPSec VPN：** 随机数生成、密钥协商、安全报文封装、NAT 穿越、身份鉴别
  * **SSL VPN：** 随机数生成、密钥协商、安全报文传输、身份鉴别、访问控制、密钥更新、客户端主机检查

**3。VPN 产品性能**

**IPSec VPN：**

  * 加解密吞吐率
  * 加解密时延
  * 加解密丢包率
  * 每秒新建连接数

**SSL VPN：**

  * 最大并发用户数
  * 最大并发连接数
  * 每秒新建连接数
  * 吞吐率

## 四、VPN 技术应用

  * 远程访问虚拟网（Access VPN）：远程办公
  * 内部虚拟网（Intranet VPN）：企业总部、分支机构、办事处连接
  * 扩展虚拟网（Extranet VPN）：合作伙伴、不同公司连接
