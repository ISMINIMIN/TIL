# 02. 데이터 타입

[예제로 배우는 Go 프로그래밍 - Go 데이터 타입](http://golang.site/go/article/5-Go-%EB%8D%B0%EC%9D%B4%ED%83%80-%ED%83%80%EC%9E%85) <br>
[GoLang 시작하기 - 02 데이터 타입](https://wikidocs.net/163791)

<br>

> ## Data Type

### 1) Boolean 타입
- `bool`
- `0` 또는 `nil`을 `false`로 변환하지 않음

<br>

### 2) Numeric 타입
- 정수형<br>
`int`, `int8`, `int16`, `int32`, `int64` <br>
`uint`, `uint8`, `uint16`, `uint32`, `uint64`, `uintptr`
- 실수형<br>
`float32`, `float64` <br>
`complex64`, `complex128` (복소수)

<br>

### 3) String 타입
- `string`
- `double quotation("")`로 둘러 선언하면, 특수 문자는 이스케이프 문자를 해석해서 처리
- `backtick(``)`으로 둘러 선언하면, 이스케이프 문자를 해석하지 않고 처리
아래의 str2는 출력시 개행하지 않음
- 복수 라인으로 선언할 수 없음
```go
str1 := "A\nA"
fmt.Println(str1)  // 츌력값 : A [개행] A

str2 := `B\nB`
fmt.Println(str2)  // 출력값 : B\nB
```

<br>

### 4) 기타 타입
- `byte` - `uint8(unsigned 8-bit)`과 동일, **아스키코드(ASCII)** 표기 가능
- `rune` - `int32(signed 32-bit)`과 동일, **유니코드(UTF-8)** 표기 가능
```go
b_chr := 97
fmt.Printf("%c", b_chr)  // 출력값 : a

r_chr := 44032
fmt.Printf("%c", r_chr)  // 출력값 : 가
```

<br>
<br>

> ## Type Conversion

### 데이터 타입 변환
데이터 타입을 변환하기 위해서는 `T(v)`와 같이 표현한다.
<br>
여기서, `T`는 변환하고자 하는 타입을, `v`는 변환할 값을 의미한다.
```go
var i int = 100
var u uint = uint(i)
var f float32 = float32(i)
fmt.Println(f, u)            // 출력값 : 100 100

str := "ABC"
bytes := []byte(str)
str2 := string(bytes)
fmt.Println(bytes)           // 출력값 : [65 66 67]
```
암묵적 변환이 일어나지 않으므로 타입을 변환하기 위해서는 명시적으로 지정이 필요하다.
<br>
**명시적 지정 없이 타입 변환이 일어나는 경우 런타임 에러가 발생한다.**