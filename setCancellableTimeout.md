 **_Problem_** : Implement a function setCancellableTimeout, that acts like setTimeout but instead of returning a timer ID, it returns a function that when called, cancels the pending callback function. The setCancellableTimeout function should have the exact same signature as setTimeout:
 function.

Example:

```
    let i = 0;
    // t = 0:
    const cancel = setCancellableTimeout(() => {
    i++;
    }, 100);
    // t = 50:
    cancel();
    // t = 100: i is still 0 because cancel() was called.

```
**_Solution 1_**:

```
    function setCancellableTimeout1(cb,delay) {
        const timerID = setTimeout(cb,delay);
        return () => {
            clearTimeout(timerID);
        }
    }


    const x = setCancellableTimeout1(() => {
        console.log('Hello world!!');
    },3000);

    x();

```



**_Solution 2_**:

```
    function setCancellableTimeout2(cb,delay) {
        let flage = true;
        setTimeout(() => {
            if(!flage) return;
            cb();
        },delay)
        return () => {
            flage = false;
        }
    }

    const y = setCancellableTimeout2(() => {
        console.log('Hello Earth!!')
    },3000);

    y();

```

