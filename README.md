# Testcase to reproduce [webpack issue #1940](https://github.com/webpack/webpack/issues/1940)
Included screenshots of me following these steps

## Steps to reproduce

1. npm install 
2. webpack

## Expected result
webpack builds each time, with export loader injecting the following code
```
lib1.js -> module.exports = internal1;
lib2.js -> module.exports = internal2;
```

## Actual result
webpack is outputting the alphabetically first query into all libs.
```
lib1.js -> module.exports = internal1;
lib2.js -> module.exports = internal1;
```
