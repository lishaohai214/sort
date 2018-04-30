## 四种排序宣发
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