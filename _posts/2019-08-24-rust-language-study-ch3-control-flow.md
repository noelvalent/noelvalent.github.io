---
layout: post 
title:  "Rust Language Study Ch1: Function"
date:   2019-08-24 21:00:00 +0900
---

이 포스트는 Rust를 공부하고 기록한 포스트입니다. 개인적으로 Rust에 관심이 있었기도 했지만, Go에 관심이 있고 같이 배우자는 팀원분의 제안에 오기가 생겨서 공부를 시작하였습니다. 현재 시스템하고 Pwnable에 관심…이 있다고 말할 실력을 갖는 것을 목표로 공부하고 있습니다.

## if 표현식

```rust
fn main() {
    let number = 6;

    if number % 4 == 0 {
        println!("number is divisible by 4");
    } else if number % 3 == 0 {
        println!("number is divisible by 3");
    } else if number % 2 == 0 {
        println!("number is divisible by 2");
    } else {
        println!("number is not divisible by 4, 3, or 2");
    }
}
```

## let구문에서 if 사용하기

if를 소개할 때 표현식이라고 소개를 했는데 표현식이기 때문에 값을 반환 값을 let 구문의 rvalue 값으로 넣어줄 수 있습니다.

```rust
fn main() {
    let condition = true;
    let number = if condition {
        5
    } else {
        6
    };

    println!("The value of number is: {}", number);
}
```

단 if와 else 에서 반환해주는 값의 타입이 다르면 에러를 출력한다.



## 반복문

loop는 rust가 그만두라고 명시하여 알려주기 전까지 코드 블럭을 반복 수행한다.

```rust
fn main() {
    loop {
        println!("again!");
    }
}
```



while은 특정 조건이 참인 동안 반복합니다.

```rust
fn main() {
    let mut number = 3;

    while number != 0 {
        println!("{}!", number);

        number = number - 1;
    }

    println!("LIFTOFF!!!");
}
```

For는 범위 기반 반복문이라고도 하며 콜렉션의 각 요소에 걸쳐 반복 수행 할 수 있습니다.

```rust
fn main() {
    let a = [10, 20, 30, 40, 50];

    for element in a.iter() {
        println!("the value is: {}", element);
    }
}
```

for는 간결하고 안전해서 보편적으로 사용되는 반복문 구조자입니다.

하지만 특정 횟수만큼 코드를 반복할 경우 while이 더 유용할 수 있습니다.

for를 특정 횟수만큼 반복할 경우 Range를 이용하기도 하는데 , .rev()를 통해 뒤집을 수 도 있습니다.

