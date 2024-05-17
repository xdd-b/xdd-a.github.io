## css
- 讲讲盒模型
- 文字单行移出省略
- flex：1 代表了什么？
- display:none，opactiy:0，visibility:hidden 区别
- 高度塌陷


## js
- 讲讲事件循环
```js

console.log('script start')
async function async1(){
    console.log('async1 start')
    await async2()
    console.log('async1 end')
}

async function async2(){
    console.log('async2 start')
    await async3()
    console.log('async3 end')
}


function async3(){
    console.log('async3')
}

new Promise((resolve,reject)=>{
    setTimeour(()=>{
    console.log('promise')
        resolve()
    },0)
}).then(()=>{
    console.log('promise then')
})

console.log('script end')
```
```js

console.log('script start')
setTimeout(()=>{
    console.log('timer_1')
    setTimeout(()=>{
        console.log('timer_3')
    },0)
    new Promise((resolve,reject)=>{
    setTimeour(()=>{
    console.log('promise')
        resolve()
    },0)
    }).then(()=>{
        console.log('promise then')
    })
},0)

setTimeout(()=>{
    console.log('timer_2')
},0)

console.log('script end')
```
- 普通函数和箭头函数的区别
- 知道怎么改变this吗？展开讲讲
- promise的方法有哪些，分别讲讲
- 写一个并发请求
```js

/**
 * promise: 所有的http请求
 * options: 配置项
 */
const { request } = useRequest(promises,{
    limit:3, //并发数量
    successFn(){
        console.log('执行了') //每一个请求成功都执行这个函数
    },
    errorFn(){
        console.log('执行了') //每一个请求失败都执行这个函数
    }
})


request().then(res=>{
    console.log(res) // 所有请求成功的数据
},err=>{
    console.log(err) // 失败了的数据
})

```



## react
- 函数组件和类组件的区别?
- 为什么函数组件不需要this ，而类组件需要this？，为什么类组件需要bind绑定this？
- react 性能优化
- interface 和 type 区别，
