<!--info-header-start--><h1>Concat <img src="https://img.shields.io/badge/-%EC%89%AC%EC%9B%80-7aad0c" alt="쉬움"/> <img src="https://img.shields.io/badge/-%23array-999" alt="#array"/></h1><blockquote><p>by Andrey Krasovsky <a href="https://github.com/bre30kra69cs" target="_blank">@bre30kra69cs</a></p></blockquote><p><a href="https://tsch.js.org/533/play/ko" target="_blank"><img src="https://img.shields.io/badge/-%EB%8F%84%EC%A0%84%ED%95%98%EA%B8%B0-3178c6?logo=typescript&logoColor=white" alt="도전하기"/></a> &nbsp;&nbsp;&nbsp;<a href="./README.md" target="_blank"><img src="https://img.shields.io/badge/-English-gray" alt="English"/></a>  <a href="./README.zh-CN.md" target="_blank"><img src="https://img.shields.io/badge/-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-gray" alt="简体中文"/></a>  <a href="./README.ja.md" target="_blank"><img src="https://img.shields.io/badge/-%E6%97%A5%E6%9C%AC%E8%AA%9E-gray" alt="日本語"/></a> </p><!--info-header-end-->

JavaScript의 `Array.concat` 함수를 타입 시스템에서 구현하세요. 타입은 두 인수를 받고, 인수를 왼쪽부터 concat한 새로운 배열을 반환해야 합니다.

예시:

```ts
type Result = Concat<[1], [2]> // expected to be [1, 2]
```

정답:

```ts
type Tuple = readonly unknown[]
type Concat<T extends Tuple, U extends Tuple> = [...T, ...U]
```

[해설](https://ghaiklor.github.io/type-challenges-solutions/ko/easy-concat.html)

> [튜플](https://velog.io/@from_numpy/TypeScript-Tuple%ED%8A%9C%ED%94%8C)
>
> 튜플은 길이와 각 요소마다의 타입이 고정된 배열이다
>
> 기존의 배열의 타입 순서를 변경하고 싶지 않을 때 사용
>
> push 등으로 배열의 길이를 바꾸는 것도 막으려면 readonly 사용
>
> ```ts
> type UserInfo = [number, string, string, string, boolean] // tuple 타입 정의
>
> // initialize correctly
> const userInfo1: UserInfo = [
>   1,
>   "user1@example.com",
>   "abcd123",
>   "1999-01-01",
>   true,
> ]
> const userInfo2: UserInfo = [
>   2,
>   "user2@example.com",
>   "abcd1234",
>   "1994-05-12",
>   false,
> ]
> const userInfo3: UserInfo = [
>   3,
>   "user3@example.com",
>   "abcd12345",
>   "2001-03-15",
>   false,
> ]
>
> // initialize incorrectly
> const userInfo4: UserInfo = [
>   "user4@example.com",
>   4,
>   true,
>   "2002-10-25",
>   "abcd123456",
> ] // Error
> ```

<!--info-footer-start--><br><a href="../../README.ko.md" target="_blank"><img src="https://img.shields.io/badge/-%EB%8F%8C%EC%95%84%EA%B0%80%EA%B8%B0-grey" alt="돌아가기"/></a> <a href="https://tsch.js.org/533/answer/ko" target="_blank"><img src="https://img.shields.io/badge/-%EC%A0%95%EB%8B%B5%20%EA%B3%B5%EC%9C%A0%ED%95%98%EA%B8%B0-teal" alt="정답 공유하기"/></a> <a href="https://tsch.js.org/533/solutions" target="_blank"><img src="https://img.shields.io/badge/-%EC%A0%95%EB%8B%B5%20%EB%B3%B4%EA%B8%B0-de5a77?logo=awesome-lists&logoColor=white" alt="정답 보기"/></a> <hr><h3>관련된 문제들</h3><a href="https://github.com/type-challenges/type-challenges/blob/main/questions/03057-easy-push/README.ko.md" target="_blank"><img src="https://img.shields.io/badge/-3057%E3%83%BBPush-7aad0c" alt="3057・Push"/></a>  <a href="https://github.com/type-challenges/type-challenges/blob/main/questions/03060-easy-unshift/README.ko.md" target="_blank"><img src="https://img.shields.io/badge/-3060%E3%83%BBUnshift-7aad0c" alt="3060・Unshift"/></a> <!--info-footer-end-->
