# unsafe Psedu-Array to Array
Ways convert Pesude-Array to Array becomes unsafe

## Astral Planes

```js
console.log(Array.from("❤").length === 2)
```

```js
for (const char of "❤") {
  console.log(char); // only one ❤
}
```

## Confusing behaviour
Original Typescript Code
```ts
const a = [...new Array(8).keys()];
console.log(a);
```

After compiling Typescript to JavaScript
```js
var __spreadArray = (this && this.__spreadArray) || function (to, from, pack) {
    if (pack || arguments.length === 2) for (var i = 0, l = from.length, ar; i < l; i++) {
        if (ar || !(i in from)) {
            if (!ar) ar = Array.prototype.slice.call(from, 0, i);
            ar[i] = from[i];
        }
    }
    return to.concat(ar || Array.prototype.slice.call(from));
};
var a = __spreadArray([], new Array(8).keys(), true);
console.log(a);
```

there is nothing in the console

## Solve the problem with Array.from

```js
Array.from(new Array(10).keys())
```
