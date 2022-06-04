# Mission (2022.05.12-05.13)
## DAY 17

### Mission 1 (원칙1)
의도가 분명한 이름을 짓는다

### Before 😣

```
let d
let elapsed
const ages = arr.map((i) => i.age)
```

### 무엇을 고치려고 하는지, 고치려는 문제가 무엇인지 알려주세요.
변수의 이름이 무엇을 뜻하는지 의미가 분명하지 않고 불용어를 사용하고 있다.
각 변수가 어떤 일을 하는지 의도가 분명히 드러나는 이름을 지어 주어야 한다.

### After 😎

```
let daysSinceModification
const agesOfUsers = users.map((user) => user.age)
```

### 어떻게 고쳤는지, 사례에서 무엇을 배워야 하는지 설명해주세요.

변수가 어떤 의도를 갖고 있는지 좀 더 명확한 이름을 지었습니다.
의미가 없는 불용어 d, i를 의미가 있는 이름으로 바꿔 주었습니다.

```
let d 
let elapsed 
-> let daysSinceModification
```
하루 이후 수정
```
const ages = arr.map((i) => i.age)
-> const agesOfUsers = users.map((user) => user.age)
```
고객의 나이


### Mission 2 (원칙2)
발음하기 쉬운 이름으로 짓는다.

### Before 😣

```
let fName, lName
let cntr

let full = false
if (cart.size > 100) {
  full = true
}
```

### 무엇을 고치려고 하는지, 고치려는 문제가 무엇인지 알려주세요.
변수 이름이 축약형으로 지어져 한눈에 보기에 무슨 뜻인지 또한 발음을 어떻게 해야 하는지
알기 어렵다. 좀더 분명하고 발음하기 명확한 이름을 지어 주어야 한다.

### After 😎
```

let firstName, lastName
let counter

const MAX_CART_SIZE = 100
// ...
const isFull = cart.size > MAX_CART_SIZE
```
### 어떻게 고쳤는지, 사례에서 무엇을 배워야 하는지 설명해주세요.

```
let fName, lName -> let firstName, lastName
let cntr -> let counter

```
변수를 축약형으로 작성하면 작성자는 편하겠지만 이것을 읽는 다른사람은 이것이 어떤 의미인지
어떻게 읽어야 하는지 혼란을 줄 수 있다. 좀 더 명확하고 발음하기 쉬운 이름을 지어 주어야 한다.

```
if (cart.size > 100)
```
에서 100은 무엇을 지칭하는지 이해하기 어렵다.
그렇기 때문에 const MAX_CART_SIZE = 100 변수 선언 한 다음에

```
const isFull = cart.size > MAX_CART_SIZE
```
사용해 주면 cart 사이즈가 max 사이즈 보다 크면 넘친다 라는 것을 명확히 알수 있다.


### Mission 3 (원칙3)
함수는 동사구 여야 하며 의도를 분명히 전달해야 한다.
의도를 표현하기 위해 주석을 달지 마라. 

### Before 😣

```
/**
 * Invite a new user with its email address
 * @param {String} user email address
 */
function inv (user) { /* implementation */ }
```
### 무엇을 고치려고 하는지, 고치려는 문제가 무엇인지 알려주세요.
함수 명이 모호하게 지어져 무슨 뜻인지 파악하기 어려운데 이를 보충하기 위해서 주석을
달고 있다. 구구절절하게 주석을 달기 보다는 명확한 함수명을 짓는 것이 타당하다.
  
### After 😎  

```
function inviteUser (emailAddress) { /* implementation */ }
```
### 어떻게 고쳤는지, 사례에서 무엇을 배워야 하는지 설명해주세요.

```
function inv (user)
```
함수의 이름과 인수 값의 이름이 어떠한 의도를 띄는지 모호 하다.

```
/**
 * Invite a new user with its email address
 * @param {String} user email address
 */ 
 ``` 
대신 주석으로 함수는 이메일 주소로 새로운 고객을 초대 한다고 설명을 달고 있다.

의도는 오로지 코드를 통해서만 들어내야 독자가 오독하는 것을 막을 수 있다.

```
function inviteUser (emailAddress)
```

함수 명은 고객을 초대하고 인수로 고객의 이메일 주소를 사용한다고 분명하게 써야한다.