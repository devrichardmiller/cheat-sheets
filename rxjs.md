# RxJS Cheat-Sheet

## Fundamental Concepts

- Obersable
- Observer
  - a JavaScript object with three methods: Next(), Error(), and Complete()
  - these methods are typically passed as an (anonymous) object with (anonymous) callback methods:
```javascript
        const someObserver = {
            next: event => console.log(`You just typed ${event.target.value}!`),
            error: err => console.log(`Oops... ${err}`),
            complete: () => console.log(`Complete!`),
        };
```
  - pass this object to the obervable's "subscribe" method to create a subscription
  - "pipe" transformations reside with the observable and take rxjs operators:
```javascript
        someObservable.pipe(
            map(item => item * 2),
            tap(console.log(item)),
            take(2)
        ).subscribe(console.log);
```
