## 피자 나눠 먹기(1)

[https://school.programmers.co.kr/learn/courses/30/lessons/120809](https://school.programmers.co.kr/learn/courses/30/lessons/120814)

---

```javascript
function solution(n) {
  let divide = n % 7 === 0 ? 0 : 1;
  return Math.floor(n / 7) + divide;
}
```

- 삼항연산자를 이용하여 n명 나누기 7조각을 했을 때, 나누어 떨어지면 0을 리턴하고 나머지가 있으면 1을 리턴하였다.

**다른 풀이**

- 풀이 방식은 같은데, 소수점 아래를 올려주는 함수 Math.ceil()을 사용하였다.

```javascript
function solution(n) {
  return Math.ceil(n / 7);
}
```

<br>

## 피자 나눠 먹기(2)

[https://school.programmers.co.kr/learn/courses/30/lessons/120811](https://school.programmers.co.kr/learn/courses/30/lessons/120815)

---

```javascript
function solution(n) {
  let pizzaOne = 6;
  while (pizzaOne % n !== 0) {
    pizzaOne += 6;
  }
  return pizzaOne / 6;
}
```

- 피자 한 판에 6조각으로, 일단 남김없이 다 먹으려면 피자 한 판을 n명으로 나눴을 때 나머지가 0이어야 한다.
- while문을 이용하여 조건식에 피자 한 판이 6의 배수가 아니면 6의 배수가 될 때까지 더해주고, 그를 다시 6으로 나눈 값을 리턴했다.

쉽게 풀 줄 알았는데 처음 접근을 너무 어렵게 했다…

<br>

## 피자 나눠 먹기(3)

[https://school.programmers.co.kr/learn/courses/30/lessons/120816](https://school.programmers.co.kr/learn/courses/30/lessons/120816)

---

```javascript
function solution(slice, n) {
  return Math.ceil(n / slice);
}
```

<br>

## 배열의 평균값

[https://school.programmers.co.kr/learn/courses/30/lessons/120817](https://school.programmers.co.kr/learn/courses/30/lessons/120817)

---

```javascript
function solution(numbers) {
  let answer = 0;
  numbers.forEach((num) => {
    answer += num;
  });
  return answer / numbers.length;
}
```

- forEach를 사용하여 평균 구하기

```javascript
function solution(numbers) {
  let length = numbers.length;
  if (length % 2 !== 0) {
    return numbers[Math.round(length / 2) - 1];
  }
  return (answer =
    ((numbers[0] + numbers[length - 1]) * (length / 2)) / length);
}
```

- 예~~전에 학교 다닐 때 수학공부했던 거 생각나서 다시 풀어봤당.

<br>

## 옷가게 할인받기

[https://school.programmers.co.kr/learn/courses/30/lessons/120818](https://school.programmers.co.kr/learn/courses/30/lessons/120818)

---

```javascript
function solution(price) {
  if (price >= 500000) return Math.floor(price * 0.8);
  else if (price >= 300000 && price < 500000) return Math.floor(price * 0.9);
  else if (price >= 100000 && price < 300000) return Math.floor(price * 0.95);
  else return price;
}
```

논리 연산자를 제대로 안 쓰고 `300000 ≤ price < 500000` 이렇게 써서 계속 에러가 났다,, 바부

<br>

## 아이스 아메리카노

[https://school.programmers.co.kr/learn/courses/30/lessons/120819](https://school.programmers.co.kr/learn/courses/30/lessons/120819)

---

```javascript
function solution(money) {
  let answer = [];
  let cup = Math.floor(money / 5500);
  let jandon = money % 5500;
  answer.push(cup, jandon);
  return answer;
}
```

<br>

## 나이 출력

[https://school.programmers.co.kr/learn/courses/30/lessons/120820](https://school.programmers.co.kr/learn/courses/30/lessons/120820)

```javascript
function solution(age) {
  let result = 2022 - age + 1;
  return result;
}
```

~~_내년엔 만 나이라던데_~~

<br>

## 배열 뒤집기

[https://school.programmers.co.kr/learn/courses/30/lessons/120821](https://school.programmers.co.kr/learn/courses/30/lessons/120821)

```javascript
function solution(num_list) {
  return num_list.reverse();
}
```
