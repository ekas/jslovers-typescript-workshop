# jslovers-typescript-workshop

Repo for TypeScript talk @JSLovers

## Why a Type System for JavaScript

- Types increase your agility when doing refactoring. It's better for the compiler to catch errors than to have things fail at runtime.
- Types are one of the best forms of documentation you can have. The function signature is a theorem and the function body is the proof.

****

## Get Started

```bash
  npm install -g typescript@next
```

TypeScript provides compile time type safety for your JavaScript code. This is no surprise given its name. The great thing is that the types are completely optional. Your JavaScript code `.js` file can be renamed to a `.ts` file and TypeScript will still give you back valid `.js` equivalent to the original JavaScript file. TypeScript is intentionally and strictly a superset of JavaScript with optional Type checking.

## Types can be Explicit, Implicit & Structural

- Implicit
  
  ```javascript
  var foo = 123;
  foo = '456'; // Error: cannot assign `string` to `number`
  ```

- Explicit

  ```javascript
  var foo: number = 123;
  foo = '123'; // Error: cannot assign a `string` to a `number`
  ```

- Structural

  ```javascript
  interface Point2D {
    x: number;
    y: number;
  }
  interface Point3D {
    x: number;
    y: number;
    z: number;
  }
  var point2D: Point2D = { x: 0, y: 10 }
  var point3D: Point3D = { x: 0, y: 10, z: 20 }
  function iTakePoint2D(point: Point2D) { /* do something */ }

  iTakePoint2D(point2D); // exact match okay
  iTakePoint2D(point3D); // extra information okay
  iTakePoint2D({ x: 0 }); // Error: missing information `y`
  ```
