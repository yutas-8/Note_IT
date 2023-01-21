---
title: Taskが完了したもの
date: 
description:Task完了のものを履歴として残す 
tags: ['Completed']
category: 
---

- Whitebox.setInternalStateについて
- Mockitテストについて
  - @Mock
    - when/ThenReturnを行うことで処理が発生する
  - @Spy
    - when/ThenReturnを入力しないで通常の処理を行う
  - @Mockとインスタンス生成の違い
  - assertメソッドの種類
  - dothowについて（例外発生のテスト）
  - doReturn/whenについて
- th:ifとth:unlessについて
- if文では左から順に実行をされる（複数ある場合、左から順で1つでも落ちればfalseとなる）
- pom.xml
- 環境変数の参照方法
  - プロパティファイルに「Key=値」を設定
  - 値を環境変数と連動する際は｛中カッコ｝を使う。
  - {環境変数:値}と記述することで「:値」の部分は一致する環境変数がなかった際に設定する内容となる
  - プログラムの方では
    - @Value("${Key}")のアノテーションをつけてフィールド値に宣言することでそのクラスで環境変数を参照して使用することができる
    - 