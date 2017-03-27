### 创建buffer的三种方式
长度创建
```javascript
let buffer = new Buffer(10); //最多显示10个字节
```

字符串创建
```javascript
let buffer = new Buffer('hello');
console.log(buffer); // <Buffer 68 65 6c 6c 6f> buffer展现的是16禁止
console.log(buffer.toString()); // hello
```

数组创建
```javascript
let buffer = new Buffer([1,2,3]);
```
### 填充
buffer.fill()
```javascript
buffer.fill(value,[offet],[end]);
//value    将要填充的数据
//offet    填充数据的开始位置，不指定默认为 0
//end      填充数据的结束位置，不指定默认为 buffer 的 长度
```

buffer.write();
```javascript
//string,往里面写的字符串 offset,偏移量 length,写入的长度 encoding 默认是utf8
buffer.write('hello');
buffer.write('word',5); //写多次必须制定偏移量
```

### 拼接
copy
```javascript
copy(targetBuffer,targetStart,sourceStart,sourceEnd)
//targetBuffer  目标buffer
//targetStart   目标的开始
//sourceStart   源的开始
//sourceEnd     源的结束
let buffer = new Buffer(9);
let buf1 = new Buffer('hello');
let buf2 = new Buffer('word');
buf1.copy(buffer);
buf2.copy(buffer,5);
console.log(buffer) //hello word
```

concat();
```javascript
concat([list],totalLength);
let buf1 = new Buffer('hello');
let buf2 = new Buffer('word');
console.log(Buffer.concat([buf1,buf2]).toString()); //hello word
```
