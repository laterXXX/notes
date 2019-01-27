# 第一级标题 `<h1>`
## 第二级标题 `<h2>`
### 第三级标题 `<h3>`
#### 第二四级标题 `<h4>`
##### 第五级标题 `<h5>`
###### 第六级标题 `<h6>`

一级标题
======================
二级标题
---------------------

----


换行<br/>



----


`字句被有背景色` 字句无背景色

> 区块引用
> > 嵌套引用
> > >三嵌套引用
> > > > 四嵌套引用

> hello world!

```
<div>   
    <div></div>
    <div></div>
    <div></div>
</div>
```

```
fun main(args: Array<String>) {
   println("Hello World!")

   println("sum = ${sum(34, 67)}")
   println("sum = ${sum(34, 67)}")
   println("sum = ${sum(34, 6, 57, 34)}")

   printSum(237, 57)
   printSum(234, 567, 8)
   vars(1, 4, 6, 78, 0, 6, 9, 8)


   val sumLambda: (Int, Int) -> Int = { x, y -> x + y }
   println("sumLambda = ${sumLambda(3, 6)}")


//    if (args.size < 2) {
//        println("Two integers expected")
//        return
//    }
   testFor()


   val a: Int = 1000
   println(a === a)//true 值相等，对象地址相等

   //经过了装箱，创建了两个不同的对象
   val boxedA: Int? = a
   val anotherBoxedA: Int? = a

   //虽然经过了装箱，但是值是相等的，都是10000
   println(boxedA === anotherBoxedA) //  false，值相等，对象地址不一样
   println(boxedA == anotherBoxedA) // true，值相等
}
```
