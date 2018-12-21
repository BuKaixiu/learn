# Javascript	[Clone]

> 	

> Step:
>
> 1. 遍历对象
>
>    ```js
>    for(var prop in object) {}
>    ```
>
> 2. 判断是不是原始值
>
>    ```js
>    typeof() === object	// 不是原始值 
>    ```
>
> 3. 判断是数组还是对象
>
>    ```js
>    // instanceof 有父子域问题 
>    // toString 一般用这个
>    // constructor 
>    ```
>
> 4. 建立相应的数组或对象
>
> 5. 递归



> Code:
>
> ```js
> var obj = {
>     name: 'xioaba',
>     age: 1,
>     card: ['visa', 'master'],
>     mother: {
>         nmae: 'buxiu',
>         age: 22,
>         husband: {
>             name: 'zhengkai',
>             age: 23,
>             card: ['money', 'car']
>         }
>     } 
> }; 
> var obj1 = {};
> 
> function deepClone(origin, target) {
>    //  兼容
>    var target = target || {},
>        toStr = Object.prototype.toString,
>        arrStr = '[Object Array]';
>     for(var prop in origin) {
>         if(typeof(origin[prop]) === 'object') {
>        		target[prop] = toStr.call(origin[prop]) === arrStr ? [] : {};
>             deepClone(origin[prop], target[prop]);
>         }else {
>         	target[prop] = origin[prop];   
>         }
>     }
> }
> ```
>
>
