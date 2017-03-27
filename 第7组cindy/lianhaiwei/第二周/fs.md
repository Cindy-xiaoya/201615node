### fs模块
##### 特点
```text
1、既有同步 又有异步
2、读取文件没有会报错
3、写入文件没有会创建
4、读取默认格式是buffer类型 encoding:null
5、写入默认格式是utf8       encoding :'utf8'
```

##### 常用的方法
```javascript
readFileSync  readFile     //读取文件
writeFileSync writeFile    //写入文件
appendFile appendFileSync  //追加写入内容
mkdirSync mkdir            //创建目录
rmdirSync rmdir            //删除目录
unlinkSync unlink          //删除文件
readdirSync readdir        //读取目录
existsSync exists          //是否存在
statSync  stat             //判断文件状态

createReadStream           //创建一个可读流
createWriteStream          //创建一个可写流

流的事件:
on('data') on('end') on('error')  on('drain') 内存空了执行  pause() 暂停 resume() 重新开始
```

##### path 模块
```javascript
let path  = require('path'); //核心模块 resolve  join
console.log(path.resolve('1.js'));//以当前路径解析出一个相对路径
console.log(path.join(__dirname,'1.js'));//相当于resolve
```
