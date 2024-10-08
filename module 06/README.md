# Module 06 - RxJS, rxMethod, and Routing

## Projects
|     |     |
| --- | --- |
| [rx Colors](./projects/rx-colors/) | Reactive X and Signals based application |
| [fun with router](./projects/fun-with-router/) | Angular Routing |



## Summary

### Reactive Programming - Continuted
#### Introduction to `RxJS` operators
* We talked about the concept of operators in math, strings and arrays
* We understood that RxJS operators create observables. 
* We saw 4 documentation web sites that serve as reference guide for reactive operators
    * [ReactiveX docs](http://reactivex.io/)
    * [RxJS docs](https://rxjs-dev.firebaseapp.com/)
    * [Rx Marbles](https://rxmarbles.com/)
    * [Rx Marble Visualizer](https://rxviz.com/)
* We covered some simple operators
    * [map](https://rxjs-dev.firebaseapp.com/api/operators/map)
    * [from](https://rxjs-dev.firebaseapp.com/api/index/function/from)
    * [filter](https://rxjs-dev.firebaseapp.com/api/operators/filter)
    * [take](https://rxjs-dev.firebaseapp.com/api/operators/take)
* We created an example that uses observable to convert color search keyword into a list of matching results (colors)
* We used the `map` operator to convert user input to results

#### Flatteners
* We talked about **Higher Order Observables** - `Observable<Observable<T>>`
* We saw how to create higher order observable using the `map` operator along with a factory method.

```typescript
const order1$ = interval(1000);
const order2$ = order1$.pipe(
    map(i => interval(1000))
);

/*
    order2$ is of type Observable<Observable<number>>
*/
```

* We understood why it's a bad practice to use `subscribe` inside `subscribe`, and therefore why it's important to "Flatten" the observable.
* We saw 4 types of flattening operators:
    - `mergeAll`, and `mergeMap` - Merges all `nexts` from all inner observables
    - `switchAll`, and `switchMap` - Subscribes always to the latest observable
    - `concatAll` and `concatMap` - Subscribes to the observables one after the other sequentially
    - `exhaustAll` and `exhaustMap` - Subscribes to observables until completion only when idle

#### `rxMethod`
- We understood what `rxMethod` is - we understood that it is a method that accepts 3 types of input
    - T
    - Observable<T>
    - Signal<T>
- We understood that it accepts a method as parameter
- We understood that the method accepts an observable and should respond to it using operators
- We saw that we can use `rxMethod` for integration between signal store and reactive services (asyncronous services)
- We saw how to connect `http` with signal store


### Routing in Angular
#### Introduction to routing
* How to use the router directives by importing the router module
* How to configure the router using `provideRouter` in `app.config`
* We created a navigation bar using the `RouterLink` directive instead of `href`
* We used `RouterLinkActive` to mark the currently selected link

#### Advanced routing
* We saw how to pass parameters to a routed component using the `withComponentInputBinding()` feature.
* We saw how to use signals to create a component that responds to parameters change
* We saw how to use the new lazy loading feature with the `loadComponent` property

