# 对象 XmlElement
XmlElement 对象表示 XML 文档中的元素

## 函数
        
### getAttribute
通过名称查询属性的值
```JavaScript
String XmlElement.getAttribute(String name);
```

调用参数:
* name - 指定查询的属性名

返回结果:
* 返回属性的值

### getAttributeNS
通过命名空间 URI 和名称来获取属性值
```JavaScript
String XmlElement.getAttributeNS(String namespaceURI,
                String localName);
```

调用参数:
* namespaceURI - 指定查询的命名空间 URI
* localName - 指定查询的属性名

返回结果:
* 返回属性的值

### setAttribute
创建或改变某个新属性
```JavaScript
XmlElement.setAttribute(String name,
                String value);
```

调用参数:
* name - 指定要设置的属性名
* value - 指定要设置的属性值

该方法把指定的属性设置为指定的值。如果不存在具有指定名称的属性，该方法将创建一个新属性

### setAttributeNS
创建或改变具有命名空间的属性
```JavaScript
XmlElement.setAttributeNS(String namespaceURI,
                String qualifiedName,
                String value);
```

调用参数:
* namespaceURI - 指定要设置的命名空间 URI
* qualifiedName - 指定要设置的属性名
* value - 指定要设置的属性值

该方法与 setAttribute 方法类似，只是要创建或设置的属性由命名空间 URI 和限定名（由名字空间前缀、冒号和名字空间中的本地名构成）共同指定。除了可以改变一个属性的值以外，使用该方法还可以改变属性的名字空间前缀

### removeAttribute
通过名称删除指定的属性
```JavaScript
XmlElement.removeAttribute(String name);
```

调用参数:
* name - 指定删除的属性名

### removeAttributeNS
通过命名空间和名称删除指定的属性
```JavaScript
XmlElement.removeAttributeNS(String namespaceURI,
                String localName);
```

调用参数:
* namespaceURI - 指定要删除的命名空间 URI
* localName - 指定删除的属性名

### hasAttribute
查询当前节点是否拥有指定名称的属性
```JavaScript
Boolean XmlElement.hasAttribute(String name);
```

调用参数:
* name - 指定查询的属性名称

返回结果:
* 如果当前元素节点拥有指定属性，则返回 true，否则返回 false

### hasAttributeNS
查询当前节点是否拥有指定命名空间和名称的属性
```JavaScript
Boolean XmlElement.hasAttributeNS(String namespaceURI,
                String localName);
```

调用参数:
* namespaceURI - 指定要查询的命名空间 URI
* localName - 指定查询的属性名称

返回结果:
* 如果当前元素节点拥有指定属性，则返回 true，否则返回 false

### getElementsByTagName
返回拥有指定名称的所有元素的 XmlNodeList
```JavaScript
XmlNodeList XmlElement.getElementsByTagName(String tagName);
```

调用参数:
* tagName - 需检索的标签名。值 &#34;*&#34; 匹配所有的标签

返回结果:
* 节点树中具有指定标记的 XmlElement 节点的 XmlNodeList 集合。返回的元素节点的顺序就是它们在源文档中出现的顺序。

该方法将遍历指定元素的子孙节点，返回一个 XmlElement 节点的 XmlNodeList 对象，表示所有具有指定标签名的文档元素。元素在返回的数组中的顺序就是它们出现在文档源代码中的顺序。

XmlDocument 接口也定义了 getElementsByTagName 方法，它与该方法相似，但遍历整个文档，而不是遍历某个元素的子孙节点。

### getElementsByTagNameNS
返回拥有指定命名空间和名称的所有元素的 XmlNodeList
```JavaScript
XmlNodeList XmlElement.getElementsByTagNameNS(String namespaceURI,
                String localName);
```

调用参数:
* namespaceURI - 指定要查询的命名空间 URI
* localName - 需检索的标签名。值 &#34;*&#34; 匹配所有的标签

返回结果:
* 节点树中具有指定标记的 XmlElement 节点的 XmlNodeList 集合。返回的元素节点的顺序就是它们在源文档中出现的顺序。

该方法与 getElementsByTagName 方法相似，只是想获取的元素的标记名被指定为命名空间 URI 和在命名空间中定义的本地名的组合。

### hasChildNodes
查询是否存在子节点
```JavaScript
Boolean XmlElement.hasChildNodes();
```

返回结果:
* 存在任何子节点时返回 true，否则返回 false

### normalize
合并相邻的 Text 节点并删除空的 Text 节点
```JavaScript
XmlElement.normalize();
```

这个方法将遍历当前节点的所有子孙节点，通过删除空的 Text 节点，已经合并所有相邻的 Text 节点来规范化文档。该方法在进行节点的插入或删除操作后，对于简化文档树的结构很有用。

### cloneNode
创建指定的节点的精确拷贝
```JavaScript
XmlNode XmlElement.cloneNode(Boolean deep = true);
```

调用参数:
* deep - 是否深度拷贝，为 true 时，被克隆的节点会克隆原节点的所有子节点

返回结果:
* 返回所复制的节点

该方法将复制并返回调用它的节点的副本。如果传递给它的参数是 true，它还将递归复制当前节点的所有子孙节点。 否则，它只复制当前节点。返回的节点不属于文档树，它的 parentNode 属性为 null。当复制的是 Element 节点时，它的所有属性都将被复制。

### lookupPrefix
返回在当前节点上匹配指定的命名空间 URI 的前缀
```JavaScript
String XmlElement.lookupPrefix(String namespaceURI);
```

调用参数:
* namespaceURI - 指定匹配的命名空间 URI

返回结果:
* 返回匹配的前缀，未匹配到返回 null

### lookupNamespaceURI
返回在当前节点上匹配指定的前缀的命名空间 URI
```JavaScript
String XmlElement.lookupNamespaceURI(String prefix);
```

调用参数:
* prefix - 指定匹配的前缀

返回结果:
* 返回匹配的命名空间 URI，未匹配到返回 null

### insertBefore
在已有的子节点前插入一个新的子节点
```JavaScript
XmlNode XmlElement.insertBefore(XmlNode newChild,
                XmlNode refChild);
```

调用参数:
* newChild - 插入新的节点
* refChild - 在此节点前插入新节点

返回结果:
* 返回新的子节点

如果文档树中已经存在了 newChild，它将从文档树中删除，然后重新插入它的新位置。来自一个文档的节点（或由一个文档创建的节点）不能插入另一个文档。也就是说，newChild 的 ownerDocument 属性必须与当前节点的 ownerDocument 属性相同。

### insertAfter
在已有的子节点后插入一个新的子节点
```JavaScript
XmlNode XmlElement.insertAfter(XmlNode newChild,
                XmlNode refChild);
```

调用参数:
* newChild - 插入新的节点
* refChild - 在此节点后插入新节点

返回结果:
* 返回新的子节点

如果文档树中已经存在了 newChild，它将从文档树中删除，然后重新插入它的新位置。来自一个文档的节点（或由一个文档创建的节点）不能插入另一个文档。也就是说，newChild 的 ownerDocument 属性必须与当前节点的 ownerDocument 属性相同。

### appendChild
向节点的子节点列表的末尾添加新的子节点
```JavaScript
XmlNode XmlElement.appendChild(XmlNode newChild);
```

调用参数:
* newChild - 指定添加的节点

返回结果:
* 返回这个新的子节点

如果文档树中已经存在了 newChild，它将从文档树中删除，然后重新插入它的新位置。来自一个文档的节点（或由一个文档创建的节点）不能插入另一个文档。也就是说，newChild 的 ownerDocument 属性必须与当前节点的 ownerDocument 属性相同。

### replaceChild
将某个子节点替换为另一个
```JavaScript
XmlNode XmlElement.replaceChild(XmlNode newChild,
                XmlNode oldChild);
```

调用参数:
* newChild - 指定新的节点
* oldChild - 指定被替换的节点

返回结果:
* 如替换成功，此方法可返回被替换的节点，如替换失败，则返回 null

如果文档树中已经存在了 newChild，它将从文档树中删除，然后重新插入它的新位置。来自一个文档的节点（或由一个文档创建的节点）不能插入另一个文档。也就是说，newChild 的 ownerDocument 属性必须与当前节点的 ownerDocument 属性相同。

### removeChild
从子节点列表中删除某个节点
```JavaScript
XmlNode XmlElement.removeChild(XmlNode oldChild);
```

调用参数:
* oldChild - 指定被删除的节点

返回结果:
* 如删除成功，此方法可返回被删除的节点，如失败，则返回 null

### dispose
强制回收对象，调用此方法后，对象资源将立即释放
```JavaScript
XmlElement.dispose();
```

### equals
比较当前对象与给定的对象是否相等
```JavaScript
Boolean XmlElement.equals(object expected);
```

调用参数:
* expected - 制定比较的目标对象

返回结果:
* 返回对象比较的结果

### toString
返回对象的字符串表示，一般返回 &#34;[Native Object]&#34;，对象可以根据自己的特性重新实现
```JavaScript
String XmlElement.toString();
```

返回结果:
* 返回对象的字符串表示

### toJSON
返回对象的 JSON 格式表示，一般返回对象定义的可读属性集合
```JavaScript
Value XmlElement.toJSON(String key = "");
```

调用参数:
* key - 未使用

返回结果:
* 返回包含可 JSON 序列化的值

### valueOf
返回对象本身的数值
```JavaScript
Value XmlElement.valueOf();
```

返回结果:
* 返回对象本身的数值

## 属性
        
### namespaceURI
查询元素的命名空间的 URI。如果选定的节点无命名空间，则该属性返回 NULL
```JavaScript
readonly String XmlElement.namespaceURI;
```

### prefix
查询和设置元素的命名空间前缀。如果选定的节点无命名空间，则该属性返回 NULL
```JavaScript
String XmlElement.prefix;
```

### localName
查询元素的本地名称。如果选定的节点无命名空间，则该属性等同于 nodeName
```JavaScript
readonly String XmlElement.localName;
```

### tagName
返回元素的标签名
```JavaScript
readonly String XmlElement.tagName;
```

### id
查询和设置元素的 id 属性
```JavaScript
String XmlElement.id;
```

### textContent
查询和设置选定元素的文本。查询时，返回元素节点内所有文本节点的值；设置时，删除所有子节点，并用单个文本节点来替换它们。
```JavaScript
String XmlElement.textContent;
```

### innerHTML
查询和设置选定元素的 HTML 文本，仅在 html 模式有效。查询时，返回元素节点内所有子节点的 HTML 编码；设置时，删除所有子节点，并用指定的 HTML 解码后替换它们。
```JavaScript
String XmlElement.innerHTML;
```

### className
查询和设置元素的 class 属性，仅在 html 模式有效
```JavaScript
String XmlElement.className;
```

### attributes
返回包含被选节点属性的 NamedNodeMap。如果被选节点不是元素，则该属性返回 NULL。
```JavaScript
readonly XmlNamedNodeMap XmlElement.attributes;
```

### nodeType
返回节点的节点类型
```JavaScript
readonly Integer XmlElement.nodeType;
```

不同对象的 nodeType 会返回不同的值：
- XmlElement: ELEMENT_NODE(1)
- XmlAttr: ATTRIBUTE_NODE(2)
- XmlText: TEXT_NODE(3)
- XmlCDATASection: CDATA_SECTION_NODE(4)
- XmlProcessingInstruction: PROCESSING_INSTRUCTION_NODE(7)
- XmlComment: COMMENT_NODE(8)
- XmlDocument: DOCUMENT_NODE(9)
- XmlDocumentType: DOCUMENT_TYPE_NODE(10)

### nodeName
返回节点的名称，根据其类型
```JavaScript
readonly String XmlElement.nodeName;
```

不同对象的 nodeName 会返回不同的值：
- XmlElement: element name
- XmlAttr: 属性名称
- XmlText: \#text
- XmlCDATASection: \#cdata-section
- XmlProcessingInstruction: 返回指定目标 target
- XmlComment: \#comment
- XmlDocument: \#document
- XmlDocumentType: doctype 名称

### nodeValue
返回节点的名称，根据其类型
```JavaScript
String XmlElement.nodeValue;
```

不同对象的 nodeName 会返回不同的值：
- XmlElement: null
- XmlAttr: 属性的值
- XmlText: 节点的内容
- XmlCDATASection: 节点的内容
- XmlProcessingInstruction: 返回指定内容 data
- XmlComment: 注释文本
- XmlDocument: null
- XmlDocumentType: null

### ownerDocument
返回节点的根元素（XmlDocument 对象）
```JavaScript
readonly XmlDocument XmlElement.ownerDocument;
```

### parentNode
可返回某节点的父节点
```JavaScript
readonly XmlNode XmlElement.parentNode;
```

### childNodes
返回指定节点的子节点的节点列表
```JavaScript
readonly XmlNodeList XmlElement.childNodes;
```

### firstChild
返回节点的首个子节点
```JavaScript
readonly XmlNode XmlElement.firstChild;
```

### lastChild
返回节点的最后一个子节点
```JavaScript
readonly XmlNode XmlElement.lastChild;
```

### previousSibling
返回某节点之前紧跟的节点（处于同一树层级），如果没有此节点，那么该属性返回 null
```JavaScript
readonly XmlNode XmlElement.previousSibling;
```

### nextSibling
返回某个元素之后紧跟的节点（处于同一树层级中），如果无此节点，则属性返回 null
```JavaScript
readonly XmlNode XmlElement.nextSibling;
```
