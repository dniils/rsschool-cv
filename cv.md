![portrait for cv](./cv-photo.png)

## Daniil Shitikov

### Contacts

- [**Telegram**](https://t.me/dniils)
- [**Github**](https://github.com/dniils)
- [**Codewars**](https://www.codewars.com/users/dniils)
- **RS School discord server nickname:** Daniil (@dniils)

### About

I have experience in developing websites, landing pages, and uncomplicated client interfaces, and am currently seeking employment or an internship as a Junior Frontend Developer or HTML Coder.

### Skills

- HTML
- CSS
- SCSS
- JavaScript
- Vue.js
- Vue Router
- Pinia
- Git
- Chrome Devtools

### Languages

- English (C1)
- Russian (Native)

### Code example

This is one of the codewars tasks (katas) I have solved.

#### Task description:

> Your task is to write a function, smartSum, that returns the sum of an arbitrary number of arguments. But be careful, some of your arguments can be arrays of numbers or nested arrays.

**My initial solution** has passed the tests, however, the code implies that we have to know the depth of nested arrays (in this case I have specified it as `const DEPTH = 3`, which was enough to pass the tests):

```javascript
function smartSum() {
  const DEPTH = 3;
  const arr = [...arguments];
  return arr.flat(DEPTH).reduce((acc, current) => acc + current, 0);
}
```

**However,** this code relies on our knowledge of `DEPTH` of an array or our ability to guess it, which makes it an unreliable solution.

**The second solution I have provided** was much better as we now do not need to know or guess the `DEPTH` before using the `smartSum()` function:

```javascript
function smartSum(...args) {
  function makeFlatFunc() {
    let result = [];

    return function flattenArray(arr) {
      for (let i = 0; i < arr.length; i++) {
        Array.isArray(arr[i]) ? flattenArray(arr[i]) : result.push(arr[i]);
      }
      return result;
    };
  }

  const flat = makeFlatFunc();
  return flat(args).reduce((a, c) => a + c, 0);
}
```

In this task (thanks to [Vadim](https://github.com/gruzdev-dev) and [javascript.info](https://javascript.info/)) I have learned about [recursive functions](https://javascript.info/recursion).
