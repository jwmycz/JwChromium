[基于电力交易业务定制的 Chromium 浏览器](https://mp.weixin.qq.com/s/J4HVe_x2va6FwFc3XQP5IQ)

[基于电力交易业务定制的 Chromium 浏览器(更新)]([微信公众平台](https://mp.weixin.qq.com/s/ElsjrzJeNQetzwp6V2EwOQ))

---
#  本次更新

###  标签页隔离优化

- **优化独立标签页 Tab**
    
- **修复部分情况下上下文混用的问题**
    
- **提升多账号同时运行的稳定性**
    

---

##  新增 `document.jwcook()` API

新增浏览器内置函数：

`document.jwcook()`

### 功能

- 获取 **HttpOnly Cookie**
    
- 可用于调试或自动化场景
    

### 示例

![f7e63e43-c464-4204-8c72-3d42f4927dbf.png](https://raw.githubusercontent.com/jwmycz/PicDown/master/gzh/2026/f7e63e43-c464-4204-8c72-3d42f4927dbf.png)	![[image-20260310141831631.png]]

##  新增 `window.JwXMLHttpRequest`

新增增强版 `XMLHttpRequest`

`new JwXMLHttpRequest()`

### 功能

- 可选择 **拦截请求响应**
    
- 与原生 `XMLHttpRequest` 保持兼容
    

### 参数说明

|参数|说明|
|---|---|
|`open=true`|开启响应拦截|
|`open=false`|等同原生 XMLHttpRequest|

### 示例代码
```
const data = JSON.stringify({});  
  
let xhr = new JwXMLHttpRequest();  
xhr.withCredentials = true;  
  
// open 为 true 时拦截响应  
xhr.open('POST','',true);  
  
xhr.setRequestHeader('Accept', 'application/json, text/plain, */*');  
xhr.setRequestHeader('Accept-Language', 'zh-CN,zh;q=0.9');  
  
xhr.onload = function() {  
    console.log(xhr.responseText);  
};  
  
xhr.send(data);
```

示例截图：

![51c94841-a448-4c40-bae8-4fa435b5baac.png](https://raw.githubusercontent.com/jwmycz/PicDown/master/gzh/2026/51c94841-a448-4c40-bae8-4fa435b5baac.png)	![[image-20260310142255777.png]]


##  新增 WebSocket 转发

支持 **WebSocket 请求与响应转发到外部端口**

### 特性

- 实时数据转发
    
- 支持请求与响应 **拦截**
    
- 可对数据进行分析或修改
    

示例：

![721cca2d-dac6-462b-b7ee-d927c83e7113.png](https://raw.githubusercontent.com/jwmycz/PicDown/master/gzh/2026/721cca2d-dac6-462b-b7ee-d927c83e7113.png)


#  原有核心能力

##  账号隔离管理

（持续优化中）

### 标签页级 Cookie 隔离

- 每个标签页拥有 **独立 Cookie / Storage**


示例：

![02829a23f184cbc40ecc063380a2dd0d.png](https://raw.githubusercontent.com/jwmycz/PicDown/master/gzh/2026/02829a23f184cbc40ecc063380a2dd0d.png)

### 多账号同时在线

- 同域名支持 **多账号并行操作**
    
- 互不污染

示例：

![21861d8a8aa073ddfe604b633f703e90.png](https://raw.githubusercontent.com/jwmycz/PicDown/master/gzh/2026/21861d8a8aa073ddfe604b633f703e90.png)

### 自动登录插件适配

- 支持自动登录插件
    
- 快速账号切换
    
---

## 🔒 安全与稳定性

### 启动鉴权机制

- 启动时 **加密校验**
    
- 支持 **使用时间 / 周期限制**
    

### Chromium 内核

- 基于 **Chromium 144**
    
- 与主流浏览器行为保持一致
    

---

##  调试与反检测能力

- **Debugger 关键字智能处理**
    
- 新增 `debugering` 关键字适配
    

### Console 日志自动落盘

日志位置：

./hooklog.txt

### 调试支持

在 **反检测模式开启时**

仍可正常进行调试

---

#  应用场景

### 多账号管理

同时登录多个账号，避免关联检测

### 安全访问

保护账号环境，降低风控风险

### 开发调试

提供稳定、安全的调试环境

---

#  下载地址

JwChromium

百度网盘：

链接: https://pan.baidu.com/s/18O8QSzI8iYquzBiE1VFG1w  
提取码: jwcz

---

<span style="color:#999;font-size:12px">
求职：有合适的爬虫岗位欢迎内推，主要意向电力辅助行业，其余也可。base:北京，西安，成都
</span>