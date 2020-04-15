# RxJS Cheat-Sheet

## Fundamental Concepts

- Obersable
  - do not use the common procedural pattern in service
  ```typescript
        getProducts(): Observable<Product[]> {
          return this.http.get<product[]>(this.productsUrl)
            .pipe(
              catchError(this.handleError)
            );
        }
  ```
  - instead use the declarative pattern
  ```typescript
        products$ = this.http.get<product[]>(this.productsUrl)
          .pipe(
            catchError(this.handleError)
          );
  ```    
  - then, in the component ...
  ```typyescript
        products$ = this.productService.products$
  ```
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
- Common Operators
  - use map() for stream data transformations
  - use tap() for debugging and other operations that do not impact data stream
  - use take() to specify the number of date items to emit through stream
  - use catchError(someFunction) to handle exceptions in prior operation
  - use filter() to reduce emit only qualified items to the stream
  - use shareReplay(1) to emit the last retrieval (from cache), rather than re-retrieval
- Higher-Order Mapping Operators
  - See [this link](https://blog.angular-university.io/rxjs-higher-order-mapping/)
  - use combineLatest() to produce a third stream from two or more streams
  - use merge()
  - use mergeMap() 
  - use forkJoin() to get multiple observables, but only once all observables are complete
  - use concatMap()
  - use switchMap()
