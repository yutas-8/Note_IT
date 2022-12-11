---
title: assertメソッド
date: 
description: 
tags: ['UT']
category: Mock
---

## assertメソッド

- booleanの値を確認する
  - ` assertTrue `
  - ` assertFalse `
- nullかどうかの確認をする
  - ` assertNull `
  - ` assertNotNull `
- 値が等しいかどうかの確認をする
  - 文字列やint等
    - > 浮動小数点（floatやdouble）は完全一致するとは限らないので、第三引数で一致する範囲（delta）を指定する
    - ` assertEquals `
    - ` assertNotEquals `
  - 配列
    - > assertEqualsで配列の比較はできない（インスタンスの比較になってしまう）
    - ` assertArrayEquals `
  - リスト
    - > ListならassertEqualsでも比較できるが、不一致だった場合に不便であるので不一致要素をを表示してくれる下記を使用する
    - ` assertIterableEquals `
  - 複数行にわたるメッセージ
    - > スタックトレースやログメッセージの比較がこれに該当する。下記は基本的にList<String>の比較だが、期待値の方に正規表現等を指定できる。
- インスタンスが同じかどうかを比較する
  - ` assertSame `
  - ` assertNotSame `
- 全チェックを実行する
  - > 他のassertメソッドはテストに失敗した時点でエラーが発生する（AssertionFailedErrorがスローされる）と、それ以降のテストは実行されない。下記を使うと１つ失敗をしても残りすべてのテストが実行される。複数失敗してもエラーがスローされるのは1回だけ（MultipleFailuresError）となる。
  - ` assertAll `
- 例外が発生することを確認する
  - > 下記の第一引数で「発生するであろう例外」のクラスを指定、第二引数でテスト対象の処理を実行する
  - ` assertThrows `
  - > 例外が発生しないことを確認する
  - ` assertDoesNotThrow `