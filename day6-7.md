## 문자열 뒤집기

[https://school.programmers.co.kr/learn/courses/30/lessons/120822](https://school.programmers.co.kr/learn/courses/30/lessons/120822)

---

```javascript
function solution(my_string) {
  let answer = [];
  return (answer = [...my_string].reverse().join(""));
}
```

- join(””)은 배열의 요소를 모두 합쳐 문자열로 반환한다.

<br>

## 짝수 홀수 개수

[https://school.programmers.co.kr/learn/courses/30/lessons/120824](https://school.programmers.co.kr/learn/courses/30/lessons/120824)

---

```javascript
function solution(num_list) {
  let evenCnt = 0;
  let oddCnt = 0;
  for (let i = 0; i < num_list.length; i++) {
    if (num_list[i] % 2 === 0) evenCnt += 1;
    else oddCnt += 1;
  }

  return [evenCnt, oddCnt];
}
```

- 다른 풀이

```javascript
function solution(num_list) {
  var answer = [0, 0];

  for (let a of num_list) {
    answer[a % 2] += 1;
  }

  return answer;
}
```

<br>

## 문자 반복 출력하기

[https://school.programmers.co.kr/learn/courses/30/lessons/120825](https://school.programmers.co.kr/learn/courses/30/lessons/120825)

```javascript
function solution(my_string, n) {
  let answer = "";
  let word = my_string.split("");
  return (answer = word.map((w) => w.repeat(n)).join(""));
}
```

<br>

## 특정 문자 제거하기

[https://school.programmers.co.kr/learn/courses/30/lessons/120826](https://school.programmers.co.kr/learn/courses/30/lessons/120826)

```javascript
function solution(my_string, letter) {
  let str = [...my_string];
  let result = [];

  for (let s of str) {
    if (s !== letter) result.push(s);
  }
  return result.join("");
}
```

- 다른 풀이

```javascript
function solution(my_string, letter) {
  return my_string.split(letter).join("");
}
```

인수 letter를 기준으로 자른 뒤 그 배열의 값들을 join(””)으로 묶어서 문자열로 반환

<br>

## 각도기

[https://school.programmers.co.kr/learn/courses/30/lessons/120829](https://school.programmers.co.kr/learn/courses/30/lessons/120829)

---

```javascript
function solution(angle) {
  let result = 0;
  if (angle < 90) return 1;
  if (angle == 90) return 2;
  if (angle < 180) return 3;
  return 4;
}
```

<br>

## 양꼬치

[https://school.programmers.co.kr/learn/courses/30/lessons/120830](https://school.programmers.co.kr/learn/courses/30/lessons/120830)

---

```javascript
function solution(n, k) {
  let answer = 0;
  const service = Math.floor(n / 10);
  //     마신 음료의 총 개수 = k (서비스 포함)
  //     k > service 면 k - service 개 * 2000
  //     else 그냥 양꼬치 계산
  if (k > service) {
    answer = 12000 * n + (k - service) * 2000;
  } else {
    answer = 12000 * n;
  }
  return answer;
}
```
