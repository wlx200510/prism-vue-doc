# 基本用法演示

引用定义：

?> 层叠样式表 (Cascading Style Sheets，缩写为 CSS），是一种样式表语言，用来描述 HTML 或 XML（包括如 SVG、XHTML 之类的 XML 分支语言）文档的呈现。CSS 描述了在屏幕、纸质、音频等其它媒体上的元素应该如何被渲染的问题。

!> 注意，这是一个警告。

输入展示性质的代码：

```javascript
const fs = require('fs')
const shell = require('shelljs')

shell.exec("rm -rf entry/entry.json")

let jsonContent = JSON.stringify({
  entry: process.argv.slice(2)
}, null, '\t')

fs.writeFile(`entry/entry.json`, jsonContent, err => {
  if (err) {
    console.log('写入失败')
    process.exit(0)
  } else {
    shell.exec("npm run dev")
  }
})
```

```css
div::-webkit-scrollbar {
  /* 这里的宽是指竖向滚动条的宽，高是指横向滚动条的高*/      
  width: 16px;      
  height: 16px;      
  background: pink;    
}
div::-webkit-scrollbar-thumb {      
  border-radius: 10px;      
  background: 
  linear-gradient(red,orange);    
}
```

在文档中插入图片：

![](https://wlx200510.github.io/prism-vue-doc/static/bd_logo.png)

文档中插入链接：

[github地址](https://github.com/wlx200510/prism-vue-doc/)