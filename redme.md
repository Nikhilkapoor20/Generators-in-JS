### Generators in Javascript 
Manual Example

```function createFlow (array) {
  let i=0;
  const inner = {
    next: function() {
      const elem = array[i];
      i++
      return elem
    }
  }
  return inner;
}

let new1 = createFlow([4,5,6]);
let new2 = createFlow([4,5,6]);

console.log(new1.next())
console.log(new1.next())
console.log(new2.next())
console.log(new1.next())

---------------------------------------

yeild Example

```function *createFlow() {
  yield 4;
    yield 5;
      yield 6;  
}

const a = createFlow();
console.log(a.next());
console.log(a.next());
console.log(a.next());
console.log(a.next());

---------------------------------------

Dynamic yield
function *createFlow() {
  const num =10;
  const newNum = yield num;
  yield 5 + newNum;
  yield 6;
}

const a = createFlow();
console.log(a.next());    
console.log(a.next(2));   // the input will directly get assigned to newNum
console.log(a.next());
console.log(a.next());