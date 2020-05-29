## Javascript 고차 함수 연습 입니다.

### 데이터

<pre>
<code>
const companies = [
  { name: "Company One", category: "Finance", start: 1981, end: 2003 },
  { name: "Company Two", category: "Retail", start: 1992, end: 2008 },
  { name: "Company Three", category: "Auto", start: 1999, end: 2007 },
  { name: "Company Four", category: "Retail", start: 1989, end: 2010 },
  { name: "Company Five", category: "Technology", start: 2009, end: 2014 },
  { name: "Company Six", category: "Finance", start: 1987, end: 2010 },
  { name: "Company Seven", category: "Auto", start: 1986, end: 1996 },
  { name: "Company Eight", category: "Technology", start: 2011, end: 2016 },
  { name: "Company Nine", category: "Retail", start: 1981, end: 1989 },
];

const ages = [33, 12, 20, 16, 5, 54, 21, 44, 61, 13, 15, 45, 25, 64, 32];
</code>
</pre>

### 반복문 for와 forEach 차이

<pre>
<code>
for (let i = 0; i < companies.length; i++) {
   console.log(companies[i]);
 }
</code>
</pre>

##### 코드가 훨씬 간결해졌다!!

<pre>
<code>
companies.forEach(function (company) {
console.log(company.name);
});
</code>
</pre>

### filter문, filter문 + 화살표 함수

<pre>
<code>
 let canDrink = [];
 for (let i = 0; i < ages.length; i++) {
    if (ages[i] >= 21) {
        canDrink.push(ages[i]);
    }
 }
</code>
</pre>

##### filter 함수는 조건에 맞는 요소들만 뽑아서 새로운 배열로 반환해준다.

<pre>
<code>
 const canDrink = ages.filter(function (age) {
    if (age >= 21) {
        return true;
    }
 });
</code>
</pre>

##### 화살표 함수를 사용하여 더 간결하게 만들었다!! (return과 function 키워드가 없어짐)

<pre>
<code>
const canDrink = ages.filter((age) => age >= 21);
</code>
</pre>

### map 함수는 반복문을 돌며 배열 안의 요소들을 1대1로 짝지어준다.

<pre>
<code>
const companyNames = companies.map(function (company) {
  return `${company.name}, ${company.start}`;
});
</code>
</pre>

##### 화살표 함수 이용

<pre>
<code>
const companyNames = companies.map((company) => `${company.name}`);
</code>
</pre>

##### map 함수로 이렇게 식을 더 해 반환 해줄수 있다.

<pre>
<code>
const agesSquare = ages.map((age) => age * 2).map((age) => age * 2);
</code>
</pre>

### Sorting 하기

<pre>
<code>
const sortedCompanies = companies.sort(function (c1, c2) {
  if (c1.start > c2.start) {
    return 1;
  } else {
    return -1;
  }
});
</code>
</pre>

##### 화살표함수와 삼항연사자를 사용했다

<pre>
<code>
const sortedCompanies = companies.sort((a, b) => (a.start > b.start ? 1 : -1));
</code>
</pre>

### for 문을 이용하여 합 구하기

<pre>
<code>
let ageSum = 0;
for (let i = 0; i < ages.length; i++) {
  ageSum += ages[i];
}
</code>
</pre>

### reduce함수를 이용하면 더욱 간단하게 만들수 있다.

##### total = accumulator, age = current라고 생각하면 된다.

<pre>
<code>
const ageSum = ages.reduce(function (total, age) {
  return total + age;
}, 0);
</code>
</pre>

##### 화살표 함수 적용

<pre>
<code>
const ageSumArrow = ages.reduce((age, total) => age + total, 0);
</code>
</pre>

##### 배웠던것 동시 적용

<pre>
<code>
const combined = ages
  .map((age) => age * 2)
  .filter((age) => age >= 40)
  .sort((a, b) => a - b)
  .reduce((a, b) => a + b, 0);
</code>
</pre>

##### combined 변수는 ages 배열 요소들을 x2하고 그중에서 40이 넘는것만 합친 값이다.
