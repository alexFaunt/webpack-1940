# Bug reproduction webpack

## BUG 1940
### Steps to reproduce

1. npm install 
2. webpack

### Expected result
webpack builds each time, with export loader injecting the following code
```
lib1.js -> module.exports = internal1;
lib2.js -> module.exports = internal2;
```

### Actual result
webpack is outputting the alphabetically first query into all libs.
```
lib1.js -> module.exports = internal1;
lib2.js -> module.exports = internal1;
```

## Duplicate identifiers 
1. npm install 
2. webpack
3. open index.html
### Expected result
duplicate identifier breaks the modules
```
Uncaught TypeError: Cannot redefine property: s
```

### Actual result
No errors 
