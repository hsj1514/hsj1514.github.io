---
layout: post
title: AngularJS 2
---


$http 이용하여 외부 API 정보 가져와서 가공하는 연습을 해봤다.
연습에 이용한 API는 2019/3/4 마이크로소프트 주가 데이터.


API 링크 : https://www.alphavantage.co/query?function=TIME_SERIES_INTRADAY&symbol=MSFT&interval=5min&apikey=demo





"index.html"
```
<!DOCTYPE html>
<html ng-app="App">
  <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.3.2/angular.min.js"></script>
  <script src="https://code.angularjs.org/1.7.7/angular-route.js"></script>
  <script src="app.js"></script>
  <link rel="stylesheet" href="app.css">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
</head>
<body>

  <div ng-controller="customersCtrl">
    <ul ng-repeat="data in stockdatas">
      <li>
        open : {{data['1. open'] | number : 3}}
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        close : {{data['4. close'] | number : 3}}
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        center : {{data['2. high']/2 + data['3. low']/2 | number : 3}}
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        volume : {{data['5. volume']}}
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
        (close - open) : {{data['4. close'] - data['1. open'] | number : 4}}
        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
      </li>
    </ul>
  </div>

</body>
</html>
```




"app.js"
```
var app = angular.module('App', ['ngRoute']);


app.controller('dataList', function($scope){
  $scope.items = [
    {'title' : 'What is Directive?',
    'content' : '특정한 행위의 기능을 가진 DOM엘리먼트.'},
    
    {'title' : 'Custom Directive',
    'content' : '디렉티브를 직접 생성해보십시오.'},
    
    {'title' : 'Bye~',
    'content' : '디렉티브 이야기를 마치겠습니다.'}
  ]
});


app.controller('CityCtrl', ['$log', '$scope', '$http', function ($log, $scope, $http) {
  $http.get('/data/country.json')
  .success(function (data) {
    $scope.addresses = data;
    $log.info('Adresslist:', $scope.addresses.addressList);
  })
  .error(function (data, status) {
    $log.error('Status:', status);
  });
}]);


app.controller('customersCtrl', ['$scope', '$http', function($scope, $http) {
  $http.get("https://www.alphavantage.co/query?function=TIME_SERIES_INTRADAY&symbol=MSFT&interval=5min&apikey=demo")
  .success(function (response){
    $scope.stockdatas = response['Time Series (5min)'];
  });
}]);
```




출력된 웹페이지
<img src="../images/stock.png"  />