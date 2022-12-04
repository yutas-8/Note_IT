---
title: Whitebox.setInternalStateついて
date: 
description: 
tags: ['Mockito']
category: UT
---

privateフィールドを置き換えることができる記述方法。
テストしたい場所に到達するまでで使用するような使い方のほうが良い。やろうと思えば何でも置き換えることができてしまい、テスト本来の意味がなくなってしまう。

```Mockito
Whitebox.setInternalState(対象クラスのインスタンス,モックするフィールド名,置き換える値);
```

- モックするフィールド名
  - 実装側で使用している変数名に該当する。
- 置き換える値
  - テストクラスの方で使用する変数名となる。
