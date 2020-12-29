- 목표: 기본 메서드들을 함수형으로 구현하여 재사용성과 가독성을 높여보자
- 프로세스: 실제 예시로 일단 코드를 구현 -> 구현한 코드에서 변수로 처리할 값들 확인 -> 구현한 코드에서 필요한 함수 확인 -> 가독성을 높임
### 구현 테스트를 위해 사용할 변수를 정의
```javascript
var users = [
    {id: 1, name: "ID", age: 36},
    {id: 2, name: "SM", age: 25},
    {id: 3, name: "KD", age: 14}
]
```
### MAP
#### 1. 실제 예시로 코드 구현(user의 age값만 가져오자)
```javascript
var new_list = [];
var i = 0;
for(i < users.length; i++) {
  new_list.push(users[i].age)
}
```
#### 2. 구현한 코드에서 변수 처리(<b>user</b>의 <b>age</b>값만 가져오자)
users는 list로 변경<br>
age는 함수로 변경
```javascript
function _map(list, iter) {
  var new_list = [];
  var i = 0;
  for(i < list.length; i++) {
    new_list.push(iter(list[i]))
  }
  return new_list
}

_map(users, function(val) { return val.age })
```
#### 3. 구현한 코드에 필요한 함수 확인
FOR문을 함수로 대체하자
```javascript
function _each(list, iter) {
  for(i < list.length; i++) {
    iter(list[i])
  }
  return list
}
```
_each 함수를 정의하면 아래와 같이 더 깔끔한 함수를 얻을 수 있다
```javascript
function _map(list, iter) {
  var new_list = [];
  _each(list, function(val){
    new_list.push(iter(val))
  })
  return new_list
}
_map(users, function(val) { return val.age })
```
### FOR문
```javascript


```
