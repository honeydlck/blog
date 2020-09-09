##2020-08-24 javascript for 、 forEach 的区别
相信很多小伙伴在编程中会疑惑 for 循环和foreach的区别，特地整理了一下：
```javascript
for(let i =0;i<=5;i++){
  console.log(i)
}f
```
```
let animals = [
  { name: 'Joey', species: 'cow' },
  { name: 'Natasha', species: 'chicken' },
  { name: 'Ed', species: 'pig' },
  { name: 'Paul', species: 'fish' },
  { name: 'Asal', species: 'cat' }
];
```
```
animals.forEach(animal=>{
  console.log(animal.name)
})
```
```
for(let i=0;i<animals.length;i++){
  console.log(animals[i].name)
}
```
区别 ：
可以说for和forEach 没有啥区别。
但是：for循环中可以break， forEach 不可以
for 循环需要临时变量i 如果多次嵌套循环，要多个临时变量 如i、j、k 等 ， 而且获取值时 需要animals[i] ；
但是用forEach ，则可以避免这个问题，且forEach 代码更少；

for 循环还有个缺点是：
Wikipedia defines an [off-by-one error](https://en.wikipedia.org/wiki/Off-by-one_error) as:

> An off-by-one error (OBOE), also commonly known as an OBOB (off-by-one bug) or “that extra inch you didn’t really want”, is a logic error involving the discrete equivalent of a boundary condition. It often occurs in computer programming when an iterative loop iterates one time too many or too few.

即循环次数有可能会不小心写错 例如
```
for (let i=0;i<=animals.length;i++)
{
console.log(animals[i]);
}
```
这段代码看着很简单，但是在 i< ,i<= 的 地方很容易多循环一次出现下标溢出。
forEach 则可以避免这个问题。

以上，大部分情形我喜欢用forEach。

与君共勉