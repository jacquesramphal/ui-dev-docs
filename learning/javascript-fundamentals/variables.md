# 2. JS Variables

- store information
- hold different types:
    - numbers, strings, booleans, undefined, symbols, objects

; (semi-colon) means END of expression

## Variable Types

```jsx
var , let, const
```

### VAR

VAR is used to define a variable

var name="Jacques";

**How to call the variable?**

```jsx
var name="Norbert";
console.log(name)
```

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2d3a21b2-4d14-4a48-a8eb-b5437eab3fdd/Screen_Shot_2021-03-11_at_9.15.18_AM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/2d3a21b2-4d14-4a48-a8eb-b5437eab3fdd/Screen_Shot_2021-03-11_at_9.15.18_AM.png)

**Numbers**

```jsx
var name="Norbert";
var number="33";

console.log(number)
```

should spit out 33 in console

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/291e6303-7c7a-4124-b825-d191f3264b42/Screen_Shot_2021-03-11_at_9.20.13_AM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/291e6303-7c7a-4124-b825-d191f3264b42/Screen_Shot_2021-03-11_at_9.20.13_AM.png)

**Using a string as a number**

Sum adds variables and displays result

```jsx
var name="Norbert";
var number="33";
var sum = name + number;

console.log(sum)
```

**Console vs Prompt**

Instead of using console log you can use PROMPT which will summon a a prompt dialog box

```jsx
var name="Norbert";
var number="33";
var sum = name + number;

// console.log(sum)
prompt(sum)
```

![https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8e9ad2d3-2b73-4561-8f04-596fa07461c9/Screen_Shot_2021-03-11_at_9.18.48_AM.png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/8e9ad2d3-2b73-4561-8f04-596fa07461c9/Screen_Shot_2021-03-11_at_9.18.48_AM.png)

**Prompt a string**

Instead of using console log you can use PROMPT which will summon a a prompt dialog box

```jsx
var name="Norbert";
var number="33";
var sum = name + number;

// console.log(sum)
prompt('What is your name')
```

![jsprompt](images/jsprompt.png)