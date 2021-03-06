# Cookie
渣渣前端第一天开始认识Cookie

## HTTP是无状态的
HTTP协议对于事务处理**没有记忆能力**，每次请求也都是独立的，服务器本身也不保存客户端的
状态，通俗的解释是：当浏览器发送请求给服务器的时候，服务器响应，但是同一个浏览器再次发
送请求给服务器的时候，服务器会响应，但是他并不知道你是刚才那个服务器，服务器不会去记住你。

> 因此为了保持连接状态，两种技术应运而生：Cookie 和 Session
> Cookie 和 Session 是相互配合的

## Cookie是什么
第一次访问网站的时候，浏览器发出请求，服务器响应请求之后，将cookie放入到响应中（发给浏览器），
保存在用户的本地；浏览器第二次发送请求的时候，就会把cookie带给服务器，服务器因此就能识别浏览
器的身份；

**此外，服务器还可以修改cookie的内容，这一步主要是通过设置响应头的Set-Cookie字段。**

> 服务器传回和浏览器传出cookie，都放置在请求/响应的头部中

## Cookie具有不可跨域性
cookie的domain字段将它绑定在了一个域名上，因此浏览器绝对不可能把一个来自taobao的
cookie发送给baidu，这将带来严重的安全问题。

## Cookie的属性（逐渐补充）

### name
cookie的名称。一个域名下绑定的cookie，name不能相同，否则会被覆盖

### value
cookie的值

### domain
cookie绑定的域名。如果没有设置，则自动绑定到当前域。

### path

### Expires/ Max-Age
有效期。Cookie默认会在关闭浏览器是自动被删除，但如果将此值设为未来的时间，
则会在过期之后失效，被浏览器删除。

### secure
HTTP是不安全的协议，当该属性为true时，cookie只会在https等安全协议下传输

### HttpOnly （重要 安全性）
若该属性设置为true，则不能通过js脚本来获取cookie，保证安全性，并有效防止xss攻击。

