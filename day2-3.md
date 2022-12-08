## 분수의 덧셈

[https://school.programmers.co.kr/learn/courses/30/lessons/120808](https://school.programmers.co.kr/learn/courses/30/lessons/120808)

---

```jsx
function solution(denum1, num1, denum2, num2) {
	let result = [];
	let d = denum1 _ num2 + denum2 _ num1; //분자
	let n = num1 * num2; //분모
	const getGCD = (a, b) => (b === 0 ? a : getGCD(b, a % b)); //최대공약수
	const gcd = getGCD(d, n);
	return (result = [d / gcd, n / gcd]);
}
```

**최소공배수(Lowest Common Divisor, LCD)**

- lcm(a, b)
- [a, b]

**최대공약수(Greatest Common Divisor, GCD)**

- gcd(a, b)
- (a, b)

**유클리드 호제법(최대공약수)**

- a > b, a와 b를 서로 나눌 때 나누어진다면 b는 최대 공약수

**기약분수 만들기**

— 분자와 분모의 최대공약수(GCD)로 약분

— 보통 **유클리드 호제법**이 효율적

## 배열 두 배 만들기

[https://school.programmers.co.kr/learn/courses/30/lessons/120809](https://school.programmers.co.kr/learn/courses/30/lessons/120809)

---

```javascript
function solution(num) {
  const result = num.map((n) => n * 2);
  return result;
}
```

map 함수 이용

- arr.map((요소, 인덱스, 배열) ⇒ { return 요소})
- 배열 안의 요소를 1:1로 짝지어 주는 것(매핑)

**다른 사람 풀이 1**

- 풀이 방식은 같은데, 프로그래머스가 제시한 함수대로 안 하고 변수로 선언해도 된다는 걸 알았다.

```javascript
const solution2 = (numbers) => numbers.map((number) => number * 2);
```

**다른 사람 풀이 2**

- reduce 함수를 사용

```javascript
function solution3(numbers) {
  return numbers.reduce((a, b) => [...a, b * 2], []);
}
```

## 중앙값 구하기

[https://school.programmers.co.kr/learn/courses/30/lessons/120811](https://school.programmers.co.kr/learn/courses/30/lessons/120811)

---

```javascript
function solution(arr) {
  arr.sort((a, b) => a - b);
  const mid = Math.round(arr.length / 2);
  return arr[mid - 1];
}
```

- 오름차순 정렬 후 배열의 길이 /2의 나머지, (반올림한 수 - 1)번째 요소 리턴

## 짝수는 싫어요

[https://school.programmers.co.kr/learn/courses/30/lessons/120813](https://school.programmers.co.kr/learn/courses/30/lessons/120813)

---

```javascript
function solution(n) {
  let arr = [];
  for (let i = 1; i <= n; i++) {
    if (i % 2 === 1) {
      arr.push(i);
    }
  }
  return arr;
}
```

- 홀수 추출 후 오름차순으로 정렬

## 최빈값 구하기

[https://school.programmers.co.kr/learn/courses/30/lessons/120812#](https://school.programmers.co.kr/learn/courses/30/lessons/120812#)

---

**제한사항**

- 0 < `array`의 길이 < 100
- **0 ≤ `array`의 원소 < 1000**

```javascript
function solution(array) {
  var answer = 0;
  if (array.length === 1) return array[0];

  console.log("array 요소의 최대값", Math.max.apply(null, array));
  let result = new Array(Math.max.apply(null, array) **+ 1**).fill(0); // **제약사항**
  console.log(result);
  for (let i = 0; i < array.length; i++) {
    result[array[i]]++;
  }

  let cnt = 0;
  for (let i = 0; i < result.length; i++) {
    if (result[i] === Math.max.apply(null, result)) {
      cnt++;
      if (cnt === 2) return -1;
    }
  }
  return result.indexOf(Math.max.apply(null, result));
}
```

1. 배열 array의 요소가 한 개면 그 자체로 최빈값이기 때문에 array[0] 리턴

2. 제시된 배열 array와 각 요소들의 빈도수를 담을 새로운 배열 result를 생성한 뒤

3. Math.max.apply(null, arr) ⇒ 배열 array의 요소 중 **최대값**을 자동으로 추출

4. 0의 자리를 만들기 위해 +1하고 (— 제한사항2 참고) fill 함수를 이용하여 각 요소에 임의의 값 0을 채우고

5. for문으로 result[array[i]] ⇒ array의 i번째의 값(숫자 그대로)의 빈도수를 카운트하여 result에 누적

```javascript
for (let i = 0; i < array.length; i++) {
  // 제약조건 0
  console.log("before :::: ", result[array[i]]);

  result[array[i]]++;
  // result[array[0]]++; result[1]
  // result[array[1]]++; result[2]
  // result[array[2]]++; result[3]
  // result[array[3]]++; result[3]
  // result[array[4]]++; result[3]
  // result[array[5]]++; result[4]

  console.log("after :::: ", result[array[i]]);
}
console.log(result);
```

<img src="https://user-images.githubusercontent.com/99732695/206472779-d29b59c2-949c-4f13-a0e1-e9050c49996a.png">

1. 최빈값이 여러 개인 경우 -1을 리턴하기 위해, 누적빈도수를 담은 배열 result[i]가 배열 array 요소의 최대값과 같으면 카운트(=최빈값의 개수)

2. 최빈값의 개수2개 이상은 무조건 -1 리턴이기 때문에, cnt가 2인 경우에 -1 리턴

~~5번 이해하는데 머리 빠개지는 줄 알았다..ㅎㅎ…~~
