## <script> 元素
### 属性 
所有属性均为可选属性
### 标签位置 
1. 放在head里面 会等js文件全部解析完成执行之后才会执行之后的html代码 页面很慢
2. 通常会放在 body的最后 在html页面加载之后执行 页面速度加快
#### saync
异步 脚本  只使用于 外部脚本文件 立即下载文件 下载后解析运行 不会有顺序 
异步加载页面其他内容 
#### charset
指定代码字符集 大多数浏览器会忽略
#### defer
延迟脚本 defer="defer" 告诉浏览器立即下载 但会延迟执行 在遇到</html>  结束标签后开始执行
顺序 第一个延迟执行脚本先执行
#### language
已经废弃
#### src
src  地址导入 ==  img src  可以放外部地址链接
如果又有嵌入代码 又有外部文件  只执行外部文件
##### 引入外部文件优点
可维护行
可缓存
适应未来
#### type
内嵌 script 代码 type="text/javascript"
## 文档模式
### 
两种模式主要影响css内容 有时也会影响js
#### 混杂模式
默认模式  
#### 标准模式
对于标准模式，可以通过使用下面任何一种文档类型来开启：
<!-- HTML 4.01 严格型 --> 
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" 
"http://www.w3.org/TR/html4/strict.dtd"> 
<!-- XHTML 1.0 严格型 --> 
<!DOCTYPE html PUBLIC 
"-//W3C//DTD XHTML 1.0 Strict//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd"> 
<!-- HTML 5 --> 
<!DOCTYPE html>
而对于准标准模式，则可以通过使用过渡型（transitional）或框架集型（frameset）文档类型来触发，
如下所示：
<!-- HTML 4.01 过渡型 --> 
<!DOCTYPE HTML PUBLIC 
"-//W3C//DTD HTML 4.01 Transitional//EN" 
"http://www.w3.org/TR/html4/loose.dtd"> 
<!-- HTML 4.01 框架集型 --> 
<!DOCTYPE HTML PUBLIC 
"-//W3C//DTD HTML 4.01 Frameset//EN" 
"http://www.w3.org/TR/html4/frameset.dtd"> 
<!-- XHTML 1.0 过渡型 --> 
<!DOCTYPE html PUBLIC 
"-//W3C//DTD XHTML 1.0 Transitional//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"> 
<!-- XHTML 1.0 框架集型 --> 
<!DOCTYPE html PUBLIC 
"-//W3C//DTD XHTML 1.0 Frameset//EN" 
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-frameset.dtd">
### <noscript>
用于在不支持javascript的浏览器中 显示代替的内容
能够包含除了<script> 标签之外的任何 HTML元素

## 小结
把 JavaScript 插入到 HTML 页面中要使用<script>元素。使用这个元素可以把 JavaScript 嵌入到
HTML 页面中，让脚本与标记混合在一起；也可以包含外部的 JavaScript 文件。而我们需要注意的地方有：
    在包含外部 JavaScript 文件时，必须将 src 属性设置为指向相应文件的 URL。而这个文件既可
以是与包含它的页面位于同一个服务器上的文件，也可以是其他任何域中的文件。
    所有<script>元素都会按照它们在页面中出现的先后顺序依次被解析。在不使用 defer 和
async 属性的情况下，只有在解析完前面<script>元素中的代码之后，才会开始解析后面
// <script>元素中的代码。
    由于浏览器会先解析完不使用 defer 属性的<script>元素中的代码，然后再解析后面的内容，
所以一般应该把<script>元素放在页面最后，即主要内容后面，</body>标签前面。
    使用 defer 属性可以让脚本在文档完全呈现之后再执行。延迟脚本总是按照指定它们的顺序执行。
    使用 async 属性可以表示当前脚本不必等待其他脚本，也不必阻塞文档呈现。不能保证异步脚
本按照它们在页面中出现的顺序执行。
另外，使用<noscript>元素可以指定在不支持脚本的浏览器中显示的替代内容。但在启用了脚本
的情况下，浏览器不会显示<noscript>元素中的任何内容