# js-
一、JS的基本数据类型
  基本数据类型：String，Boolean，Number，Undefined，Null；
  引用数据类型：Object(Array，Date，RegExp，Function)；
  基本数据类型和引用数据类型的区别：
  1、保存位置不同：基本数据类型保存在栈内存中，引用数据类型保存在堆内存中，然后在栈内存中保存了一个对堆内存中实际对象的引用，即数据在堆内存中的地址，JS对引用数据类型的操作都是操作对象的引用而不是实际的对象，如果obj1拷贝了obj2，那么这两个引用数据类型就指向了同一个堆内存对象，具体操作是obj1将栈内存的引用地址复制了一份给obj2，因而它们共同指向了一个堆内存对象；
    为什么基本数据类型保存在栈中，而引用数据类型保存在堆中？
    1）堆比栈大，栈比堆速度快；
    2）基本数据类型比较稳定，而且相对来说占用的内存小；
    3）引用数据类型大小是动态的，而且是无限的，引用值的大小会改变，不能把它放在栈中，否则会降低变量查找的速度，因此放在变量栈空间的值是该对象存储在堆中的地址，地址的大小是固定的，所以把它存储在栈中对变量性能无任何负面影响；
    4）堆内存是无序存储，可以根据引用直接获取；
按引用访问：js不允许直接访问保存在堆内存中的对象，所以在访问一个对象时，首先得到的是这个对象在堆内存中的地址，然后再按照这个地址去获得这个对象中的值；
ECMAScript中所有函数的参数都是按值来传递的，对于原始值，只是把变量里的值传递给参数，之后参数和这个变量互不影响，对于引用值，对象变量里面的值是这个对象在堆内存中的内存地址，因此它传递的值也就是这个内存地址，这也就是为什么函数内部对这个参数的修改会体现在外部的原因，因为它们都指向同一个对象；
2、基本数据类型使用typeof可以返回其基本数据类型，但是NULL类型会返回object，因此null值表示一个空对象指针；引用数据类型使用typeof会返回object，此时需要使用instanceof来检测引用数据类型；
3、定义引用数据类型需要使用new操作符，后面再跟一个构造函数来创建；
1）使用new操作符创建对象；

var obj1 = new Object();
obj1.a = 1;

2）使用对象字面量表示法创建对象；

var obj1 = {
  a: 1,
  b: 2
}

3）可以通过点表示法访问对象的属性，也可以使用方括号表示法来访问对象的属性；

  ES6新增数据类型：Map，Set，Generator，Symbol
  本地对象：ECMA-262 把本地对象（native object）定义为“独立于宿主环境的 ECMAScript 实现提供的对象”，即本地对象就是 ECMA-262 定义的类（引用类型）；
  宿主对象：宿主”就是我们网页的运行环境，即“操作系统”和“浏览器”，所有非本地对象都是宿主对象（host object），即由 ECMAScript 实现的宿主环境提供的对象，所有的BOM和DOM对象都是宿主对象，因为其对于不同的“宿主”环境所展示的内容不同，即ECMAScript官方未定义的对象都属于宿主对象，因为其未定义的对象大多数是自己通过ECMAScript程序创建的对象；
  JS内置对象：是指JS语言自带的一些对象，供开发者使用，这些对象提供了一些常用的或是最基本而必要的功能；
  1、Arguments：函数参数集合；
  2、Array对象：length,instanceof,isArray(),toString()返回字符串,valueOf()返回数组的值,join()可以将数组转为字符串,push(),pop(),shift(),unshift(),reverse(),sort(),
  slice(),splice(),indexOf(),lastIndexOf(),迭every(),filter(),forEach(),map(),some(),
  归并方法reduce(),reduceRight()；
  3、Boolean：布尔对象；
  4、Error：异常对象；
  5、Number：数值对象；
  6、String对象：length,charAt()返回指定位置的字符,concat(),slice(),subString(),
  subStr(),indexOf(),lastIndexOf(),trim(),toLowerCase(),toUpperCase(),split(),
  text.match(),text.splice()；
  7、Date对象：toUTCstring(),getTime()；
  8、RegExp对象：test()；
  9、Function对象：arguments,this,apply(this,arguments),call(this,num1,num2)；
  10、Math对象：min(),max(),ceil(),floor(),round(),random()；
  11、Global对象：encodeURI,encodeURIComponent，parseInt(),eval()；
  12、Object对象：prototype,constructor；
  基本包装类型：Boolean,Number,String
  1、转换为数值：parseInt()专门用于把字符串转换成数值,Number()用于任何类型；
  2、非字符转换成字符：toString()；
  3、数组转成字符：join()；
  4、字符串转换成数组：split()；
