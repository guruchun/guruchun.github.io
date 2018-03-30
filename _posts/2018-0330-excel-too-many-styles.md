---
layout: post
title: Excel 오류, 셀서식이 너무 많습니다
category: [office]
tags: [excel, cell styles, vba, macro]
---

## 엑셀 작업 중 "셀서식이 너무 많습니다" 오류 해결

아래와 같이 vba macro를 사용해서 지우는 것이 가장 편하다.
``` vba
Sub RemoveInvalidStyles()
'
' Remove Invalid Styles
'
On Error Resume Next
    Application.ScreenUpdating = False
    styleCount = ActiveWorkbook.Styles.Count
    Set wsResult = Worksheets("MacroResult")
    If wsResult Is Nothing Then
        Worksheets.Add.Name = "MacroResult"
    End If
    Worksheets("MacroResult").Cells(1, 1) = "Before Styles: " & styleCount
    
    dispRow = 2
    For i = styleCount To 1 Step -1
        If Not ActiveWorkbook.Styles(i).BuiltIn And ActiveWorkbook.Styles(i) <> "Normal" Then
            If ActiveWorkbook.Styles(i).Locked Then
                ActiveWorkbook.Styles(i).Locked = False
            End If
            'ActiveWorkbook.Styles(i).NameLocal = "abc_" & i
            ActiveWorkbook.Styles(i).Delete
            
errHandler:
            If Err.Number <> 0 Then
                Worksheets("MacroResult").Cells(dispRow, 2) = ActiveWorkbook.Styles(i).Name
                dispRow = dispRow + 1
                Err.Number = 0
            End If
        End If
        'Sleep (1)
    Next
    
    errStyles = "After Styles: " & styleCount & vbCrLf & "After Styles: " & ActiveWorkbook.Styles.Count
    MsgBox (errStyles)
    Worksheets("MacroResult").Cells(dispRow, 1) = "After Styles: " & ActiveWorkbook.Styles.Count
    
    Application.ScreenUpdating = True
End Sub
```

하지만 다음과 같이 
