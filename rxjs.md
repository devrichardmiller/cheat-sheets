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
  - use map() for stream data transformations
  - use tap() for debugging and other operations that do not impact data stream
  - use take() to specify the number of date items to emit through stream
  - use catchError(someFunction) to handle exceptions in prior operation
