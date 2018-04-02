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

스타일 이름이 잘못되어 있는 경우 style.Delete가 동작하지 않는다. 
* 아직 해결방법을 못찾았다. 
* 엑셀에서 직접 style 이름을 변경하고 매크로를 돌리면 지워지는데
* `ActiveWorkbook.Styles(i).NameLocal = "abc_" & i` 처럼 코드에서 이름을 변경하려고 하면 에러가 발생한다.
  * `컴파일 오류: 인수의 개수나 속성 지정이 잘못되었습니다.`
``` console
C￥AØ_XD AOA¾AIA¤ 
C￥AØ_WIPER 
C￥AØ_SMG-CKD-d1.1 
C￥AØ_Sheet1_1_1.SUMMARY 
C￥AØ_Sheet1 (2)_1.SUMMARY 
C￥AØ_RDTR99ML 
C￥AØ_MKN-M1.1 
C￥AØ_lx-taxi 
C￥AØ_laroux_2_°³¹ßAIA¤ 
C￥AØ_1.SUMMARY 
C￥AØ_°³¹ßAIA¤  (2)_°³¹ßAIA¤ 
C￥AØ_¸nA÷ 
C￥AØ_¡ßFO AoAUºnºn±³ 
AÞ¸¶_SMG-CKD-d1.1 
AÞ¸¶_Sheet1_XD AOA¾AIA¤ 
AÞ¸¶_Sheet1 (2)_1.SUMMARY 
AÞ¸¶_SAMPLE 
```
