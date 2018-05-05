
## n种排序算法

----------

```html
<body>
    <script>
        // 在实际工作经常会出现这样一个问题：后台返回一个数组中有i个json数据，需要我们根据json中某一项进行数组的排序
        let result = [
            {id: 2, name:'中国银行'},
            {id: 12, name:'北京银行'},
            {id: 3, name:'广州银行'},
            {id: 7, name:'上海银行'},
        ]
        // 现在我们根据业务需要，要根据id的大小进行排序，按照id小的json到id大的json顺序重新排列数组的顺序

        // 在js中添加排序的方法：
        // 语法：arrayObject.sort(sortby)  sortby:可选，规定排序顺序。必须是函数
        // 如果调用该方法时没有使用参数，将按字母顺序对数组中的元素进行排序，说得更精确点，是按照字符编码的顺序进行排序。要实现这一点，首先应把数组的元素都转换成字符串（如果有必要），以便进行比较。

        // 如果想按照其他标准进行排序，就需要提供比较函数，该函数比较两个值，然后返回一个用于说明这两个值的相对顺序的数字。比较函数应该具有两个参数 a 和 b， 其返回值如下：
        // 若 a 小于 b，在排序后的数组中 a 应该出现在 b之前，则返回一个 小于 0 的值。
        // 若 a 大于 b， 则返回一个大于 0 的值。

        // 下面开始使用 sort(sortby) 来进行整个排序，并打印到控制台：
        console.log(result.sort((a , b) => a.id - b.id))  
         /* (4) [{…}, {…}, {…}, {…}]
            0: {id: 2, name: "中国银行"}
            1: {id: 3, name: "广州银行"}
            2: {id: 7, name: "上海银行"}
            3: {id: 12, name: "北京银行"}
            length: 4__proto__: Array(0)  
         */
    </script>
</body>
```
```html
<body>
    <h1>js 自带的排序算法</h1>
    <script>
        
        var t = [1, 6, 2, 5, 2, 9]
        console.log(t.sort((a, b,) => a -b ))
    </script>
</body>
```

```html
<body>
    <h1>2 - 选择排序方法</h1>
    <script>
        var t = [1, 33, 5,'a', 23, 22, 9] 

        // console.log(t.sort().sort((a, b) => a - b))
        t.sort(); // 先把字符 往后放
        function f(t){
            var minIndex = 0;
            var temp = 0;
            if(t == null || t.length == 0){ return;}

            for(var i = 0; i < t.length - 1; i++){
                minIndex = i; // 无序区的最小数据数组下标

                // 在无序区中找找到最小数据并保存其数组下标
                for(var j = i + 1; j < t.length; j++){
                    if(t[j] < t[minIndex]){
                        minIndex = j;
                    }
                }
                // 如果不是无序区的最小值位置不是默认的第一个数据，则交换之。
                if(minIndex != j){
                    temp = t[i];
                    t[i] = t[minIndex];
                    t[minIndex] =temp;
                }
            }
            return t;
        }
        console.log(f(t))
    </script>
</body>
```

```html
<body>
    <h1>3 - 冒泡排序方法</h1>
    <script>
        var t = [1, 83, 33, 5,'a', 23, 77,22, 9] 
        t.sort()
        for(var i = 0; i < t.length - 1; i++){
            for(var j = i + 1; j < t.length - 1; j++){
                if(t[i] > t[j]){
                    var temp = t[i];
                    t[i] = t[j];
                    t[j] = temp;
                }
            }
        }
        console.log(t)
    </script>
</body>
```

```html
<body>
    <h1>4-插入排序算法</h1>
    <script>
        var t = [1, 83, 33, 5,'a', 23, 77,22, 9] 
        t.sort()
        function f(t){
            if(t == null || t.length < 2){
                return t;
            }
            for(var i = 1;i < t.length; i ++){
                for(var j = i; j > 0; j --) {
                    if(t[j] < t[j - 1]){
                        var temp = t[j - 1];
                        t[j - 1 ] = t[j];
                        t[j] = temp;
                    }else{
                        break;
                    }
                }
            }
            return t;
        }
        console.log(f(t))
    </script>
</body>
```


### [十大算法详解](http://www.cnblogs.com/liyongshuai/p/7197962.html)