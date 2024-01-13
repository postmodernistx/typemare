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

## Interface with dynamic keys
```ts
interface ISomeDynamicObject {
  [key: number]: SomeOtherArrayType[];
}
// or
const someObject: Record<number, SomeOtherArrayTyp[]> = {};
```

## Define a range of numbers
```ts
type Enumerate<N extends number, Acc extends number[] = []> = Acc['length'] extends N
  ? Acc[number]
  : Enumerate<N, [...Acc, Acc['length']]>;

type IntRange<F extends number, T extends number> = Exclude<Enumerate<T>, Enumerate<F>>;

class SingleCard {
  suit: 'clubs' | 'diamonds' | 'hearts' | 'spades';
  rank: IntRange<1, 13>;
}
```

## Get keys from interface and use as type in another interface
```ts
interface INutritionalValues {
  calcium: 0;
  iron: 0;
}

interface IField {
  id: keyof INutritionalValues; // must be calcium or iron as defined in INutritionalValues
}
```

## I hate my dev life
```ts
// @ts-ignore
```
