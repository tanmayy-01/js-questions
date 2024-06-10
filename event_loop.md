**_Problem_** : Tell the output of the following code.

```
console.log('start');
setTimeout(() => {
    process.nextTick(() => {
        console.log('inside the timeout');
    })
},0);

Promise.resolve().then(() => {
    console.log('Promise 1');
})

process.nextTick(() => {
    console.log('outside the timeout');
})

setTimeout(() => {
    console.log('timeout');
},0);
```

**_Solution_**:

```
start
outside the timeout
Promise 1
inside the timeout
timeout
```
