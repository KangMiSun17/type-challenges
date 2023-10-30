<!--info-header-start--><h1>Exclude <img src="https://img.shields.io/badge/-%EC%89%AC%EC%9B%80-7aad0c" alt="쉬움"/> <img src="https://img.shields.io/badge/-%23built--in-999" alt="#built-in"/> <img src="https://img.shields.io/badge/-%23union-999" alt="#union"/></h1><blockquote><p>by Zheeeng <a href="https://github.com/zheeeng" target="_blank">@zheeeng</a></p></blockquote><p><a href="https://tsch.js.org/43/play/ko" target="_blank"><img src="https://img.shields.io/badge/-%EB%8F%84%EC%A0%84%ED%95%98%EA%B8%B0-3178c6?logo=typescript&logoColor=white" alt="도전하기"/></a> &nbsp;&nbsp;&nbsp;<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>  <a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>  <a href="./README.ja.md" target="_blank"><img src="https://img.shields.io/badge/-%E6%97%A5%E6%9C%AC%E8%AA%9E-gray" alt="日本語"/></a> </p><!--info-header-end-->

`T`에서 `U`에 할당할 수 있는 타입을 제외하는 내장 제네릭 `Exclude<T, U>`를 이를 사용하지 않고 구현하세요.

예시:

```ts
type Result = MyExclude<"a" | "b" | "c", "a"> // 'b' | 'c'
```

정답:

```ts
type MyExclude<T, U> = T extends U ? never : T
```

[T 에 U 타입이 있으면 제거하겠다는 뜻](https://ghaiklor.github.io/type-challenges-solutions/ko/easy-exclude.html)

## omit 과의 차이점

https://j-ungry.tistory.com/353

Omit : 객체 형태의 타입에서 특정한 프로퍼티들을 제외 시켜줌 ( 객체 에서 프로퍼티 를 제외 )

Exclude : 여러개의 타입이 함께 존재하는 유니언 타입에서 특정 타입을 제거해준다 ( 타입 에서 타입 을 제외 )

### Exclude

```ts
// enum 을 선언
enum Languages {
  KOREAN = "kr",
  ENGLISH = "en",
  JAPANESE = "jp",
}

// Exclude 를 사용해서 제외할 수 있다.
type WithoutJapan = Exclude<Languages, Languages.JAPANESE>

// work
const kor: WithoutJapan = Languages.KOREAN
// error : 제외한 JAPANESE 를 불러오려해 에러가 난다
const eng: WithoutJapan = Languages.JAPANESE
```

### Omit

```ts
// error : Omit 을 사용하면 제외 되지 않는다
type WithoutKorean = Omit<Languages, Languages.KOREAN>

// 실제 제외되지 않았기 때문에 정상 동작한다
const withoutKor: WithoutKorean = Languages.KOREAN
console.log(withoutKor)
```

<!--info-footer-start--><br><a href="../../README.ko.md" target="_blank"><img src="https://img.shields.io/badge/-%EB%8F%8C%EC%95%84%EA%B0%80%EA%B8%B0-grey" alt="돌아가기"/></a> <a href="https://tsch.js.org/43/answer/ko" target="_blank"><img src="https://img.shields.io/badge/-%EC%A0%95%EB%8B%B5%20%EA%B3%B5%EC%9C%A0%ED%95%98%EA%B8%B0-teal" alt="정답 공유하기"/></a> <a href="https://tsch.js.org/43/solutions" target="_blank"><img src="https://img.shields.io/badge/-%EC%A0%95%EB%8B%B5%20%EB%B3%B4%EA%B8%B0-de5a77?logo=awesome-lists&logoColor=white" alt="정답 보기"/></a> <!--info-footer-end-->
