# Javascript 고차 함수 연습 입니다.

### 반복문 for와 forEach 차이

<pre>
<code>


for (let i = 0; i < companies.length; i++) {
   console.log(companies[i]);
 }

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

 const canDrink = ages.filter(function (age) {
    if (age >= 21) {
        return true;
    }
 });

const canDrink = ages.filter((age) => age >= 21);
</code>
</pre>
