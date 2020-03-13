# jwt

jwt用户认证
<https://www.jianshu.com/p/180a870a308a>


## 服务接口

### 登录

用户使用账户登录，成功后为用户返回token。token存在一定的有效期。

### api接口请求

请求一般api接口时，需要header携带token进行访问。

### 登出

也需要携带token，服务端注销token，也就是该token就失效了，尽管该token有效期还没有到，但它不能再使用了。

### token检查

检查token是否为空，是否过期，是否正确，以及是否失效。

## 流程图

![flow](./images/jwt-TB-1.svg)
