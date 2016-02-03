# Steps to reproduce

npm install 

webpack = normal build works fine

webpack = repeat build works fine

edit modules/module2.js
import module1 from './module1'; -> import module3 from './module3';

webpack = build outputs 'module.exports = internal1' into BOTH libs

webpack = build works fine again
