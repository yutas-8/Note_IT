---
title: Excel VBAコード集
description: Excelでよく使用する作業を自動化
tags: ['VBA']
category: Excel
---

## 全シート 倍率100% かつ A1選択状態

```VBA

Sub Zoom100()
    Dim objSheet As Worksheet
    Dim i As Integer
    
    ' ブックの表示されている全シートに対して処理を実施
    For i = 0 To ActiveWorkbook.Worksheets.Count - 1
        Set objSheet = Worksheets(ActiveWorkbook.Worksheets.Count - i)
        
        ' 非表示のシートは整形対象外
        If objSheet.Visible = True Then
            objSheet.Select
            
            ' 表示倍率の変更
            ActiveWindow.Zoom = 100
            ' 左上(A1セル)に移動
            Range("A1").Select
        End If
    Next

End Sub

```

倍率を変更すれば､作業時と提出時を自動化することが可能

## 吹き出し作成

```VBA

Sub 吹き出し作成()
    Dim balloonShape As Shape
    
    ' 吹き出しを作成
    Set balloonShape = ActiveSheet.Shapes.AddShape(msoShapeRoundedRectangularCallout, 100, 100, 150, 100)
    
    ' 吹き出しのテキストを設定
    balloonShape.TextFrame.Characters.Text = ""
    
    ' 塗りつぶし色を設定 (RGB(255, 242, 204))
    balloonShape.Fill.ForeColor.RGB = RGB(255, 242, 204)
    
    ' 枠線色を設定 (RGB(197, 90, 17)) および枠線の太さを設定 (1.5ポイント)
    With balloonShape.Line
        .ForeColor.RGB = RGB(197, 90, 17)
        .Weight = 1.5
    End With
    
    ' 吹き出しの位置調整
    ' 吹き出しからの右方向距離
    balloonShape.Left = balloonShape.Left - 30
    ' 吹き出しからの下方向距離
    balloonShape.Top = balloonShape.Top - 140
End Sub

```

## 赤枠作成

```VBA

Sub 赤枠作成()
    Dim redBorder As Shape
    
    ' 青い枠を作成
    Set redBorder = ActiveSheet.Shapes.AddShape(msoShapeRectangle, 100, 100, 150, 100)
    
    ' 塗りつぶしを非表示にする
    redBorder.Fill.Visible = msoFalse
    
    ' 枠線色を設定 (RGB(255, 0, 0)) および枠線の太さを設定 (1.5ポイント)
    With redBorder.Line
        .ForeColor.RGB = RGB(255, 0, 0) ' 赤い枠の色
        .Weight = 1.5
    End With
End Sub

```