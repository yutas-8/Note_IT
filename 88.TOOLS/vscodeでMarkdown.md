---
title: vscodeでMarkdown
description: Markdown使用時の設定の色々
tags: ['Markdown', 'vscode']
category: vscode
---

## プレビューのCSS設定

```css
h1 {
    position: relative;
    color: #158b2b;
    font-size: 20px;
    padding: 10px 0;
    text-align: center;
    margin: 1.5em 0;
  }
  h1:before {
    content: "";
    position: absolute;
    top: -8px;
    left: 50%;
    width: 150px;
    height: 58px;
    border-radius: 50%;
    border: 5px solid #a6ddb0;
    border-left-color: transparent;
    border-right-color: transparent;
    -webkit-transform: translateX(-50%);
    transform: translateX(-50%);
  }

  h2 {
    color: #505050;/*文字色*/
    padding: 0.5em;/*文字周りの余白*/
    //display: inline-block;/*文字分の枠幅になる*/
    line-height: 1.3;/*行高*/
    background: #dbebf8;/*背景色*/
    vertical-align: middle;
    border-radius: 25px 0px 0px 25px;/*左側の角を丸く*/
  }
  
  h2:before {
    content: '✓';
    color: white;
    margin-right: 8px;
  }

  h3 {
    font-weight: bold;
    padding: 0.3em 1em 0.5em;
    border-radius: 0 0 0 10px;
    border-left: 3px solid #dbebf8;/*背景色*/
    border-bottom: 3px solid #dbebf8;/*背景色*/
    position: relative;
  }
  h3::before, h3:after {
    content: '';
    height: 0;
    width: 0;
    border: solid transparent;
    position: absolute;
    left: 30px;
  }
  h3::before {
    border-color: transparent;
    border-top-color: #dbebf8;/*背景色*/
    border-right-color: #dbebf8;/*背景色*/
    border-width: 10px;
    top: 100%;
    left: 26px;
  }
  h3:after {
    border-color: transparent;
    border-top-color: #fff;
    border-right-color: #fff;
    border-width: 6.5px;
    top: 99%;
  }
```

## 拡張機能

- Markdown All in One
- Markdown Preview Enhanced
- Paste Image
- Foam
- Marp
- indent-rainbow
- Japanese Language Pack for Visual Studio Code
- Material Icon Theme
- Prettier - Code formatter

## スニペットの設定

### スニペットの保存場所

`ファイル > ユーザ設定 > ユーザスニペット構成`

### スニペットの保存

Markdownの場合は(`markdown.json`が開かれるはず)
ファイル内にスニペットの内容を作成

```json
{
  "vsnote_template_tags": {
    //スニペットを呼び出すキーワード
    "prefix": "template_tags",
    //スニペットの内容
    "body": [
      "---",
      "title: $1",
      "description: $2",
      "tags: ['$3']",
      "category: $4",
      "---",
      "\n",
    ],
    //スニペットの説明
    "description": "Markdownノートのタグ用Template"
  }
}
```

### スニペットをキーボードショートカットに登録

`ファイル > ユーザ設定 > キーボードショートカット`を開く
右上にある｢Open Keyboard Shortcuts (JSON)｣を押下して`keybindings.json`を開く
下記のようにショートカットを設定する

```json
[
    {
        "key": "ctrl+alt+a", // 任意のキーを選択
        "command": "editor.action.insertSnippet",
        "when": "editorTextFocus",
        "args": {
            "langId": "markdown",
            "name": "vsnote_template_tags" // スニペットの名前
        }
    }
]

```

保存して閉じると使用できるようになっている
