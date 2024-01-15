# 01. 변수와 상수

[예제로 배우는 Go 프로그래밍 - Go 변수와 상수](http://golang.site/go/article/4-Go-%EB%B3%80%EC%88%98%EC%99%80-%EC%83%81%EC%88%98)

<br>

> ## Variable

### 1) 변수 선언

변수는 `var` 키워드를 사용하여 선언하며, `var` 키워드 뒤에 변수명을 적고 그 뒤에 변수 타입을 적는다.
<br>
**선언된 변수가 사용되지 않는다면 에러가 발생하므로 사용되지 않는 변수는 삭제해야 한다.**
```go
var i int
i = 10

var f float32 = 10.0
```

동일한 타입의 변수가 여러개 있는 경우, 변수명을 나열하고 마지막에 타입을 한번만 지정할 수 있다.
<br>
복수 변수로 선언한 상황에서도 초기값을 지정할 수 있으며, 초기값은 순서대로 변수에 할당된다.
```go
var i, j, k int
i = 1
j = 2
k = 3

var a, b, c int = 1, 2, 3
```

<br>

### 2) 타입 추론

할당되는 값을 보고 타입 추론이 가능하다.
```go
var i = 1
var s = "Hi"
```

<br>

### 3) Short Assignment Statement

Short Assignment Statement(`:=`)을 사용하여 변수 선언이 가능하다.
<br>
단, 함수 내에서만 사용할 수 있으며 함수 밖에서는 `var` 키워드를 꼭 사용해야 한다.

```go
func main() {
  a := 1
}
```

<br>
<br>

> ## Constant

### 1) 상수 선언

상수는 `const` 키워드를 사용하여 선언하며, `const` 키워드 뒤에 상수명을 적고 그 뒤에 상수 타입을 적은 후 상수값을 할당한다.
```go
const i int = 10
const s string = "Hi"
```
변수와 마찬가지로 타입 추론이 가능하므로 상수 타입 생략 가능하다.
```go
const i = 10
const s = "Hi"
```
여러 개의 상수들을 묶어서 지정가능하며, 괄호 안에 상수들을 나열하여 사용한다.
```go
const (
  Hello = "Hello"
  World = "World"
)
```

<br>

### 2) iota
여러 개의 상수를 묶어서 지정하는 경우, 상수값을 0부터 순차적으로 부여하기 위해 `iota` 식별자를 사용할 수 있다. 
```go
const (
  Apple = iota // 0
  Grape        // 1
  Orange       // 2
)