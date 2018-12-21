## Welcome to Bu Learn Pages

You can use the [editor on GitHub](https://github.com/BuKaixiu/learn/edit/gh-pages/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### deepClon

[deepClon](https://github.com/BuKaixiu/learn/blob/master/javaScript/clone/clone.html)

```markdown
function deepClone(origin, target) {
   //  兼容
    var target = target || {},
       toStr = Object.prototype.toString,
       arrStr = '[Object Array]';
    
    for(var prop in origin) {
        // 判断是否是自身属性 去除继承
        if(origin.hasOwnProperty(prop)) {
            
        	if(origin[prop] !== 'null' && typeof(origin[prop]) === 'object') {
                
       		    target[prop] = toStr.call(origin[prop]) === arrStr ? [] : {};
           		deepClone(origin[prop], target[prop]);
            }else {
                target[prop] = origin[prop];   
            }
        }
    }
    return target;
}
```
