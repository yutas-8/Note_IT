---
title: doメソッド
date: 
description: Mockテストで使用するメソッド
tags: ['UT']
category: Mock
---

## doReturn/when

` doReturn(戻り値).when(Mock化 or Spy化した クラス名).メソッド名(引数 基本any()) `

- Mock化されたメソッド、Spy化されたメソッドに対して戻り値を設定できる。
- when/Returnではできない。Spy化したメソッドにも戻り値を指定することができる。
- まれに が使えない場合あり

## doThrow

- 強制的に例外を発生させて例外のテストをすることができる。

```java
doThrow(new RuntimeException()).when(mock).someVoidMethod();
doThrow(RuntimeException.class).when(mock).someVoidMethod();
doThrow(RuntimeException.class, BigFailure.class).when(mock).someVoidMethod();
```

- `doThrow()` 例外で void メソッドをスタブ化したい場合に使用する。
- `when(Object)` void をスタブ化するには、コンパイラが括弧内のvoidメソッドを好まない。
- `toBeThrown` スタブ化されたメソッドが呼び出されたときにスローされる。（パラメーター）
- `戻り値` スタブの方法を選択する。
