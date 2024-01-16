# 03. 함수

[예제로 배우는 Go 프로그래밍 - Go 함수](http://golang.site/go/article/9-Go-%ED%95%A8%EC%88%98) <br>
[쉽고 빠른 Go 시작하기 - Functions part One, Functions part Two](https://nomadcoders.co/go-for-beginners/lectures/1503)

<br>

> ## Function

### 1) 함수 선언
- 매개변수와 반환값이 없는 함수
    ```go
    func sayHello() {
        fmt.Println("Hello")
    }
    ```
- 매개변수가 없고, 반환값이 있는 함수
    ```go
    func getHello() string {
        str := "Hello"
        return str
    }
    ```
- 매개변수가 있고, 반환값이 없는 함수
    ```go
    func sayThis(idx int, this string) {
        fmt.Println(idx, this)
    }
    ```
- 매개변수와 반환값이 있는 함수
    ```go
    func lenAndUpper(name string) (int, string) {
	return len(name), strings.ToUpper(name)
    }
    ```

    <br>
    <br>

> ## Parameter

### 1) Pass By Value
- 인자값을 복사해서 전달하는 방식
- 함수 안에서 연산을 하더라도 원래 값은 변하지 않음
```go
package main

import "fmt"

func printName(name string) {
    name = "sum"
	fmt.Println(name)
}

func main() {
    name := "min"
    printName(name)
    fmt.Println(name)
}
```
```
sum
min
```

<br>

### 2) Pass By reference
- 주소값을 전달하는 방식
- 함수 안에서 연산을 하면 원래 값도 변함
- `&` : 주소
- `*` : 참조
```go
package main

import "fmt"

func printName(name *string) {
    *name = "sum"
	fmt.Println(*name)
}

func main() {
    name := "min"
    printName(&name)
    fmt.Println(name)
}
```
```
sum
sum
```

<br>

### 3) 가변 인자
- N개의 동일한 타입의 매개변수를 전달
```go
package main

import "fmt"

func printWords(words ...string) {
	fmt.Println(words)
}

func main() {
    printWords("apple", "banana", "cherry", "durian")
	printWords("alpha", "bravo", "charlie")
}
```
```
[apple banana cherry durian]
[alpha bravo charlie]
```