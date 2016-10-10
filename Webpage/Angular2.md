## .then

然后来看看这个then怎么使用（主要是如何从中提取出我们需要的后台返回的数据）：
[javascript] view plain copy
uploadQuantityLoader(params).then(function(Cquantity){  
        $scope.quantityMap = Cquantity.quantityMap;  
        makeGraph();      
    });  
then(fn) 方法中带一个参数，这个参数就是要被执行的函数，并且，这个作为参数的函数本身有一个参数，这个参数就是我们需要的数据，这里是关键，本例中也就是
Cquantity，然后这个Cquantity就可以放在函数里面进行处理了。
反正绕了一大圈，我们真正需要的就是其中的数据。

## subscribe

[JavaScript-观察者模式(publish/subscribe)](http://blog.csdn.net/qiqingjin/article/details/51345542)

## =>

a => print(a);
等同于
function(a){print(a);}

详见ES6

## .find

getHero(id: number) {
  return this.getHeroes()
             .then(heroes => heroes.find(hero => hero.id === id));
}