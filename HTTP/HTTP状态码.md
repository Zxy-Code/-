# HTTP状态码
## 总说

1XX 消息

2XX 成功

3XX 重定向

4XX 客户端错误

5XX 服务器错误

1XX 100-101信息提示

2XX 200-206成功

3XX 300-305重定向

4XX 400-415客户端错误

5XX 500-505服务器错误

## 常见的状态码

200 OK 服务器成功处理了请求（这个是我们见到最多的）

301/302 Moved Permanently（重定向）请求的URL已移走。Response中应该包含一个Location URL, 说明资源现在所处的位置

304 Not Modified（未修改）客户的缓存资源是最新的， 要客户端使用缓存

404 Not Found 未找到资源

501 Internal Server Error服务器遇到一个错误，使其无法对请求提供服务

## 细说

200OK服务器成功处理了请求（这个是我们见到最多的）HTTP协议详解-200

201Created（已创建）对于那些要服务器创建对象的请求来说，资源已创建完毕。

202Accepted（已接受）请求已接受， 但服务器尚未处理

203Non-Authoritative Information（非权威信息）服务器已将事务成功处理，只是实体Header包含的信息不是来自原始服务器，而是来自资源的副本。

204No Content(没有内容)Response中包含一些Header和一个状态行， 但不包括实体的主题内容（没有response body）状态码204

205Reset Content(重置内容)另一个主要用于浏览器的代码。意思是浏览器应该重置当前页面上所有的HTML表单。

206Partial Content（部分内容）部分请求成功状态码206

301和302 非常相似，  一个是永久转移，一个是临时转移。

（SEO中，搜索引擎如果碰到301， 比如网页A用301重定向到网页B，搜索引擎可以肯定网页A永久性改变地址，就会把网页B当做唯一有效目标）

302，303，307 是一样。  这是因为302是HTTP 1.0定义的， HTTP1.1中使用303,307. 同时又保留了302.  （但在现实中，我们还是用302，我是没见过303和307）

所以这一节， 我们只需要掌握302， 304 就可以了。

状态码状态消息含义实例

300Multiple Choices（多项选择）客户端请求了实际指向多个资源的URL。这个代码是和一个选项列表一起返回的，然后用户就可以选择他希望的选项了

301Moved Permanently（永久移除)请求的URL已移走。Response中应该包含一个Location URL, 说明资源现在所处的位置状态码301

302Found（已找到）与状态码301类似。但这里的移除是临时的。 客户端会使用Location中给出的URL，重新发送新的HTTP requestHTTP协议详解-302

303See Other（参见其他）类似302

304Not Modified（未修改）客户的缓存资源是最新的， 要客户端使用缓存HTTP协议之缓存-304

305Use Proxy（使用代理）必须通过代理访问资源， 代理的地址在Response 的Location中

306未使用这个状态码当前没使用

307Temporary Redirect（临时重定向类似302

400Bad Request（坏请求）告诉客户端，它发送了一个错误的请求。状态码400

401Unauthorized（未授权）需要客户端对自己认证HTTP协议之基本认证-401

402Payment Required（要求付款）这个状态还没被使用， 保留给将来用

403Forbidden（禁止）请求被服务器拒绝了状态码403

404Not Found（未找到）未找到资源HTTP协议详解-404

405Method Not Allowed（不允许使用的方法）不支持该Request的方法。状态码405

406Not Acceptable（无法接受）

407Proxy Authentication Required(要求进行代理认证)与状态码401类似， 用于需要进行认证的代理服务器HTTP协议之代理-407

408Request Timeout（请求超时）如果客户端完成请求时花费的时间太长， 服务器可以回送这个状态码并关闭连接

409Conflict（冲突）发出的请求在资源上造成了一些冲突

410Gone（消失了）服务器曾经有这个资源，现在没有了， 与状态码404类似

411Length Required（要求长度指示）服务器要求在Request中包含Content-Length。状态码411

412Precondition Failed（先决条件失败）

413Request Entity Too Large（请求实体太大）客户端发送的实体主体部分比服务器能够或者希望处理的要大状态码413

414Request URI Too Long（请求URI太长）客户端发送的请求所携带的URL超过了服务器能够或者希望处理的长度状态码414

415Unsupported Media Type（不支持的媒体类型）服务器无法理解或不支持客户端所发送的实体的内容类型

416Requested Range Not Satisfiable（所请求的范围未得到满足）

417Expectation Failed（无法满足期望）

500Internal Server Error(内部服务器错误)服务器遇到一个错误，使其无法为请求提供服务状态码500

501Not Implemented（未实现）客户端发起的请求超出服务器的能力范围(比如，使用了服务器不支持的请求方法)时，使用此状态码。状态码501

502Bad Gateway（网关故障）代理使用的服务器遇到了上游的无效响应状态码502

503Service Unavailable（未提供此服务）服务器目前无法为请求提供服务，但过一段时间就可以恢复服务

504Gateway Timeout（网关超时）与状态吗408类似， 但是响应来自网关或代理，此网关或代理在等待另一台服务器的响应时出现了超时

505HTTP Version Not Supported（不支持的HTTP版本）服务器收到的请求使用了它不支持的HTTP协议版本。 有些服务器不支持HTTP早期的HTTP协议版本，也不支持太高的协议版本状态码505

