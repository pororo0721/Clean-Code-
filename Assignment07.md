# Mission(2022.04.30-05.01)
## DAY 10

### Mission 1
### BAD 더러운 코드 😣
### Hint❕ : 검색하기 쉬운 이름을 사용하세요.
### blastOFF는 로켓 발사를 의미. 86400000은 하루의 밀리초 (milliseconds) 의미. 

### What the heck is 86400000 for?
setTimeout(blastOff, 86400000);

### GOOD 😎
### 위 코드를 깨끗하게 다시 작성해 주세요.

const oneHour = 60*60*1000;
const milliseconds = oneHour;
const blastOffTime = 24 * milliseconds;

setTimeout(blastOff, blastOffTime);

### 어떻게 고쳤는지, 사례에서 무엇을 배워야 하는지 설명해주세요.

86400000 숫자의 의미가 불분명 하기 때문에 처음 이 코드를 보면 무엇을 지칭하는지
알아내는데 한참 시간이 걸린다. 
우선 한 시간은 3600000 밀리초 이고 3600000은 한 시간이다.
변수로 oneHour을 계산하고 이것이 밀리초 임을 설정한다. 
86400000은 하루의 밀리초 (milliseconds) 의미하기 때문에 
blastOffTime이라는 변수를 만들어 하루 24시간을 밀리초에 곱해주면 86400000 숫자가 나올 것이다.
따라서 덩그러니 아무 설명 없이 숫자를 넣어 주는것 보다는 이것이 어떠한 의미를 담고 있는지
변수로 설명해 주면 좀 더 코드를 읽기 쉬울것이다.

### Mission 2
### BAD 더러운 코드 😣
### Hint❕ : 의미있는 이름을 사용해주세요.

const yyyymmdstr = moment().format("YYYY/MM/DD");

### GOOD 😎
### 위 코드를 깨끗하게 다시 작성해 주세요.

const formatDate = moment().format("YYYY/MM/DD");

### 어떻게 고쳤는지, 사례에서 무엇을 배워야 하는지 설명해주세요.
yyyymdstr은 년,달,날짜를 string으로 작성한다? 라는 어느정도 의미를 유추 할 수 있지만 책에서 언급한 바와 같이 이 변수 명을 사용한다면 팀원들과 '와이와이와이엠에스티알' 이렇게 불러야 할것이다. 프로그래밍은 사회 활동이기 때문에 이와 같은 변수 명을 쓴다면 발음하기도 토론하기도 어려울 것이다.
  
날짜를 설정하는 변수이므로 그 역할에 맞게 formatDate로 설정하면 그 변수에 역할을 잘 들어 내면서 발음 하기도 다른 사람과 토론하기도 쉽지 않을까 생각한다. 

### Mission 3
### BAD 더러운 코드 😣
### Hint❕ : 불필요하게 반복하지 마세요.

const Car = {
  carMake: "Honda",
  carModel: "Accord",
  carColor: "Blue"
};

function paintCar(car, color) {
  car.carColor = color;
}

### GOOD 😎
### 위 코드를 깨끗하게 다시 작성해 주세요.

const Car = {
    carMake: 'Honda',
    carModel: 'Accord',
    carColor: 'red',
  paint: function(color) {
    this.carColor = color;
  }
};

const myCar = Object.create(Car);

myCar.paint('blue');
console.log(myCar.carColor);
console.log(Car.carColor);

### 어떻게 고쳤는지, 사례에서 무엇을 배워야 하는지 설명해주세요.
paintCar 함수에 car, color라는 두 개의 인수가 들어가 있고 심지어 인수 car는 변수 Car와 이름이 동일하다. 혼란을 일으킬 수 있다고 생각한다.
Car 변수 안에 paint 함수를 생성해서 인수로 받은 color로 색깔만 변경 할 수 있도록 하면 어떨까 생각해 보았다.

만일 나의 차를 빨강에서 파랑으로 바꾸고 싶다면 myCar이라는 변수를 생성해서 인수로 기존 car를 넣어 주고 paint함수를 통해서 파랑을 넣는다면 파랑을 색칠 할 것이라는 의미가 분명해 지지 않을까 생각한다. 
완벽한 코드는 아니라고 생각하지만 인수를 최대한 단항으로 넣으려고 노력해 보았다.

