---
layout: post
title: "テストフレームワークを導入する(mocha)"
date: 2016-04-13 08:04:24 +0900
comments: true
categories: make_online_judge tech
---

ユーザのサインアップ、ログイン・ログアウトを実装できたので
いよいよ本格的に機能を作りこんでいきたいのですが、
やはりテストが無いと不安です。

今回は、比較的シンプルそうなテストフレームワーク [mocah](http://mochajs.org/) を導入します。

+ [mocah](http://mochajs.org/)

```
$ npm install -g mocha --save-dev
```


さっそく動かしてみる.


```
$ mkdir test
$ touch test/test.js
```

```js
describe('Array', function() {
  describe('#indexOf()', function () {
    it('should return -1 when the value is not present', function () {
      assert.equal(-1, [1,2,3].indexOf(5));
      assert.equal(-1, [1,2,3].indexOf(0));
    });
  });
});
```

```
$ mocha
```

```
Array
  #indexOf()
    1) should return -1 when the value is not present


0 passing (14ms)
1 failing

1) Array #indexOf() should return -1 when the value is not present:
   ReferenceError: assert is not defined
    at Context.<anonymous> (test/test.js:4:7)
```
