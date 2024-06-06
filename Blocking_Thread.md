 **_Problem_** : Implement a function blockingMainThread, which intentionally block our main thread for specefic amount of time 

 Example:

```
   function blockingMainThread (ms) {
    // logic
   }

   blockingMainThread(2000) // blocking main thread for 2 sec

```

**_Solution_**:

```
    function blockingMainThread (ms) {
        let timeNow = new Date().getTime();
        while(new Date().getTime() < timeNow + ms) {

            // wait
        }
    }

    blockingMainThread(3000)    // blocking main thread for 3 sec

```