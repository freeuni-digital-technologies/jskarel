# JsKarel

### Code Coverage
<!-- these lines are automatically updated by istanbul-badges-readme -->

![Statements](https://img.shields.io/badge/statements-96.74%25-brightgreen.svg?style=flat)
![Branches](https://img.shields.io/badge/branches-100%25-brightgreen.svg?style=flat)
![Functions](https://img.shields.io/badge/functions-92.85%25-brightgreen.svg?style=flat)
![Lines](https://img.shields.io/badge/lines-96.58%25-brightgreen.svg?style=flat)

### Installation
```shell
yarn add jskarel
```

### Usage
```typescript
import { Karel } from 'jskarel'
const world = {
   width: 5,
   height: 5,
   walls: [
       // wall between 1x1 and 2x1
       { first: {x: 1, y:1}, second: {x: 2, y:1}} 
   ],
   beepers: [{x: 1, y:1}, {x: 2, y: 1}]
}
const karel = new Karel({
    world: world
});
karel.move(); // throws exception because there is a wall
karel.pickBall(); // beeper on 1x1 has been picked up
karel.turnLeft();
karel.move();
expect(karel.position).eql({x: 1, y:2});
expect(karel.world.beepers[0]).eql({x:2, y:1});
```