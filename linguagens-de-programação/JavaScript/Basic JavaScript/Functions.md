## Function() constructor
- expressão new;
- criar um novo objeto;
- this keyword.

```js
function Person(name, age) {
    this.name = name
    this.age = age

}
const luther = new Person("Luther", 23)
console.log(luther)

```

## arrow function
```js
const sayMyName = (name) => {
	console.log(name)
}

sayMyName("Luther")
```

#javascript 