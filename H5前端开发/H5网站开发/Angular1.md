# AngularJS

## 父子Controller间通信

《[AngularJs 父子级Controller传递数据](http://qiaolevip.iteye.com/blog/2154634)》

#### 子级传递数据给父级 

```javascript
// 子级传递  
$scope.checkLoggedIn = function(type) {  
          $scope.transferType = type;  
          $scope.$emit('transfer.type', type);  
}  
  
// 父级接收  
$scope.$on('transfer.type', function(event, data) {  
          $scope.transferType = data;  
        });  
        $scope.checkLoggedIn = function() {  
          var type = $scope.transferType;  
}
```

#### 父级传递数据给子级

```javascript
// 父级传递  
$scope.transferType = '';  
$scope.checkLoggedIn = function(type) {  
          $scope.transferType = type;  
          $scope.$broadcast('transfer.type', type);  
}  
  
// 子级接收  
$scope.transferType = '';  
$scope.$on('transfer.type', function(event, data) {  
          $scope.transferType = data;  
        });  
        $scope.checkLoggedIn = function() {  
          var type = $scope.transferType;  
} 
```

## $watch

## ng-show和ng-if

## ng-class

《[AngularJS ng-class用法](http://my.oschina.net/gejiawen0913/blog/188547)》

## $http

《[AngularJS中$http服务的简单用法](http://www.2cto.com/kf/201506/405137.html)》

## js判断是否为空

```javascript
var exp = null;
if (!exp && typeof(exp)!="undefined" && exp!=0)
{
    alert("is null");
}
```

尽管如此，我们在 DOM 应用中，一般只需要用 (!exp) 来判断就可以了，因为 DOM 应用中，可能返回 null，可能返回 undefined，如果具体判断 null 还是 undefined 会使程序过于复杂。

