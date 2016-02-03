# Testcase to reproduce [webpack issue #1940](https://github.com/webpack/webpack/issues/1940)
Included screenshots of me following these steps

## Steps to reproduce

1. npm install 
2. webpack
3. webpack
4. edit modules/module2.js
  ```import module1 from './module1'; -> import module3 from './module3';```
5. webpack
6. webpack

## Expected result
webpack builds each time, with export loader injecting the following code
```
lib1.js -> module.exports = internal1;
lib2.js -> module.exports = internal2;
```

## Actual result
In step 5, which is the first build since the edit the exports are incorrect
```
lib1.js -> module.exports = internal1;
lib2.js -> module.exports = internal1;
```
In step 6, it returns to normal despite no further changes being made.
