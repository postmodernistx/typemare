# typemare
TypeScript nightmares (solved?)

## error TS2339: Property 'id' does not exist on type
```
data.id;
(<any>data).id; //access id like if data has no type
```

## gsap/Vue callback for transitions
```js
function onEnter(el: HTMLElement, done: gsap.Callback) {}
```

## padStart is not defined
In `tsconfig.json`
```js{3}
{
  "compilerOptions": {
     "lib": ["es6", "es2017", "es2017.string", "dom"],
  }
}
```
