---
title: Asynchrone Rückgabetypen (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 07890291-ee72-42d3-932a-fa4d312f2c60
ms.openlocfilehash: 6fffd94a4b9ca531af58138b7613e0b3c5364c56
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498410"
---
# <a name="async-return-types-visual-basic"></a>Asynchrone Rückgabetypen (Visual Basic)
Asynchrone Methoden haben drei mögliche Rückgabetypen: <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.Task> und den void-Typ. In Visual Basic wird der void-Rückgabetyp als [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)-Prozedur geschrieben. Weitere Informationen zu asynchronen Methoden finden Sie unter [asynchrone Programmierung mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 Jeder Rückgabetyp wird in einem der folgenden Abschnitte untersucht und am Ende des Themas wird ein vollständiges Beispiel aller drei Typen verwenden.  
  
> [!NOTE]
>  Um das Beispiel ausführen zu können, muss Visual Studio 2012 oder höher sowie .NET Framework 4.5 oder höher auf Ihrem Computer installiert sein.  
  
##  <a name="BKMK_TaskTReturnType"></a> Task(T)-Rückgabetyp  
 Die <xref:System.Threading.Tasks.Task%601> -Rückgabetyp wird für eine asynchrone Methode, die enthält verwendet eine [zurückgeben](../../../../visual-basic/language-reference/statements/return-statement.md) Anweisung, die in der der Operand vom Typ ist `TResult`.  
  
 Im folgenden Beispiel enthält die asynchrone `TaskOfT_MethodAsync`-Methode eine "return"-Anweisung, die eine ganze Zahl zurückgibt. Aus diesem Grund muss die Methodendeklaration den Rückgabetyp `Task(Of Integer)` haben.  
  
```vb  
' TASK(OF T) EXAMPLE  
Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.FromResult is a placeholder for actual work that returns a string.  
    Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
    ' The method then can process the result in some way.  
    Dim leisureHours As Integer  
    If today.First() = "S" Then  
        leisureHours = 16  
    Else  
        leisureHours = 5  
    End If  
  
    ' Because the return statement specifies an operand of type Integer, the   
    ' method must have a return type of Task(Of Integer).   
    Return leisureHours  
End Function  
```  
  
 Wenn `TaskOfT_MethodAsync` aus einem "await"-Ausdruck aufgerufen wird, ruft der "await"-Ausdruck den ganzzahligen Wert ab (der Wert von `leisureHours`), der in der Aufgabe gespeichert wird, die von `TaskOfT_MethodAsync` zurückgegeben wird. Weitere Informationen zu await-Ausdrücken, finden Sie unter [Await-Operator](../../../../visual-basic/language-reference/operators/await-operator.md).  
  
 Der folgende Code ruft auf und erwartet die `TaskOfT_MethodAsync`-Methode. Das Ergebnis wird der `result1`-Variablen zugewiesen.  
  
```vb  
' Call and await the Task(Of T)-returning async method in the same statement.  
Dim result1 As Integer = Await TaskOfT_MethodAsync()  
```  
  
 Sie können die Vorgehensweise besser verstehen, wenn Sie den Aufruf von `TaskOfT_MethodAsync` von der Anwendung von `Await` trennen, wie der folgenden Code zeigt. Ein Aufruf der `TaskOfT_MethodAsync`-Methode, die nicht sofort eine Antwort erwartet, gibt ein `Task(Of Integer)` zurück, wie Sie es von der Deklaration der Methode erwarten. Die Aufgabe wird im Beispiel der `integerTask`-Variablen zugewiesen. Da `integerTask` eine <xref:System.Threading.Tasks.Task%601> ist, enthält es eine <xref:System.Threading.Tasks.Task%601.Result>-Eigenschaft des Typs `TResult`. In diesem Fall stellt TResult einen ganzzahligen Typ dar. Wenn `Await` auf `integerTask` angewendet wird, wertet der „await“-Ausdruck den Inhalt der Eigenschaft <xref:System.Threading.Tasks.Task%601.Result%2A> von `integerTask` aus. Der Wert wird der `result2`-Variablen zugewiesen.  
  
> [!WARNING]
>  Die <xref:System.Threading.Tasks.Task%601.Result%2A>-Eigenschaft ist eine Blocking-Eigenschaft. Wenn Sie darauf zuzugreifen versuchen, bevor seine Aufgabe beendet ist, wird der momentan aktive Thread blockiert, bis die Aufgabe abgeschlossen und der Wert verfügbar ist. In den meisten Fällen sollten Sie auf den Wert zugreifen, indem Sie `Await` verwenden, anstatt direkt auf die Eigenschaft zuzugreifen.  
  
```vb  
' Call and await in separate statements.  
Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
' You can do other work that does not rely on resultTask before awaiting.  
textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
Dim result2 As Integer = Await integerTask  
```  
  
 Die Anzeigeanweisungen im folgenden Code überprüfen, dass die Werte der `result1`-Variable, der `result2`-Variable und der `Result`-Eigenschaft gleich sind. Beachten Sie, dass die `Result`-Eigenschaft eine Blocking-Eigenschaft ist und nicht darauf zugegriffen werden sollte, bevor die Aufgabe abgeschlossen wurde.  
  
```vb  
' Display the values of the result1 variable, the result2 variable, and  
' the resultTask.Result property.  
textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
```  
  
##  <a name="BKMK_TaskReturnType"></a> Aufgabenrückgabetyp  
 Asynchrone Methoden, die keine return-Anweisung enthalten oder eine return-Anweisung enthalten, die keinen Operanden zurückgibt, haben normalerweise einen Rückgabetyp von <xref:System.Threading.Tasks.Task>. Solche Methoden wäre [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) Verfahren aus, wenn sie für eine synchrone Ausführung geschrieben wurden. Wenn Sie einen `Task`-Rückgabetyp für eine asynchrone Methode verwenden, kann ein aufrufende Methode einen `Await`-Operator verwenden, um den Abschluss des Aufrufers anzuhalten, bis die aufgerufene asynchrone Methode beendet ist.  
  
 Im folgenden Beispiel enthält die asynchrone `Task_MethodAsync`-Methode keine "return"-Anweisung. Daher geben Sie einen `Task`-Rückgabetyp für die Methode an, die `Task_MethodAsync` ein Warten ermöglicht. Die Definition des `Task`-Typs enthält keine `Result`-Eigenschaft, um einen Rückgabewert zu speichern.  
  
```vb  
' TASK EXAMPLE  
Async Function Task_MethodAsync() As Task  
  
    ' The body of an async method is expected to contain an awaited   
    ' asynchronous call.  
    ' Task.Delay is a placeholder for actual work.  
    Await Task.Delay(2000)  
    textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
    ' This method has no return statement, so its return type is Task.   
End Function  
```  
  
 `Task_MethodAsync` wird aufgerufen und erwartet, indem eine "await"-Anweisung anstelle eines "await"-Ausdrucks verwendet wird, ähnlich der Aufrufanweisung für ein synchrones `Sub` oder eine Methode, die "void" zurückgibt. Die Anwendung von einem `Await` Operator in diesem Fall erzeugt keine Werte.  
  
 Der folgende Code ruft auf und erwartet die `Task_MethodAsync`-Methode.  
  
```vb  
' Call and await the Task-returning async method in the same statement.  
Await Task_MethodAsync()  
```  
  
 Wie im vorherigen <xref:System.Threading.Tasks.Task%601> beispielsweise können Sie den Aufruf von trennen `Task_MethodAsync` von der Anwendung von einem `Await` -Operator, wie im folgenden Code gezeigt. Beachten Sie jedoch, dass `Task` über keine `Result`-Eigenschaft verfügt und dass kein Wert erzeugt wird, wenn ein Erwartungsoperator auf `Task` angewendet wird.  
  
 Der folgende Code trennt Aufrufe von `Task_MethodAsync` vom Erwarten der Aufgabe, die `Task_MethodAsync` zurückgibt.  
  
```vb  
' Call and await in separate statements.  
Dim simpleTask As Task = Task_MethodAsync()  
  
' You can do other work that does not rely on simpleTask before awaiting.  
textBox1.Text &= String.Format(vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf)  
  
Await simpleTask  
```  
  
##  <a name="BKMK_VoidReturnType"></a> Rückgabetyp „Void“  
 Der primäre Verwendungszweck `Sub` Prozeduren wird in den Ereignishandlern, es ist kein Rückgabetyp (bezeichnet als einen void-Rückgabetyp in anderen Sprachen). Eine "void"-Rückgabe kann auch verwendet werden, um Methoden mit einer "void"-Rückgabe zu überschreiben, oder auch für Methoden, die "Fire-and-Forget"-Aktivitäten ausführen. Sie sollten nach Möglichkeit immer eine `Task` zurückgeben, da eine "void" zurückgebende asynchrone Methode nicht erwartet werden kann. Jeder Aufrufer einer solchen Methode muss in der Lage sein, in seiner Ausführung bis zum Abschluss fortzufahren, ohne auf die aufgerufene asynchrone Methode zu warten, und der Aufrufer muss unabhängig von den Werten oder Ausnahmen sein, die die asynchrone Methode generiert.  
  
 Der Aufrufer einer "void" zurückgebenden asynchronen Methode kann die von der Methode ausgelöste Ausnahmen nicht behandeln, und solche Ausnahmefehler können möglicherweise zu Fehlern in der Anwendung führen. Wenn eine Ausnahme in einer asynchronen Methode auftritt, die <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurückgibt, wird die Ausnahme in der zurückgegebenen Aufgabe gespeichert und erneut ausgelöst, wenn die Aufgabe erwartet wird. Stellen Sie daher sicher, dass jede asynchrone Methode, die eine Ausnahme erstellen kann, über den Rückgabetyp <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> verfügt und die Aufrufe der Methode erwartet werden.  
  
 Weitere Informationen zum Auffangen von Ausnahmen in async-Methoden finden Sie unter [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally-Anweisung).  
  
 Der folgende Code definiert einen asynchrone Ereignishandler.  
  
```vb  
' SUB EXAMPLE  
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
  
    textBox1.Clear()  
  
    ' Start the process and await its completion. DriverAsync is a   
    ' Task-returning async method.  
    Await DriverAsync()  
  
    ' Say goodbye.  
    textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."  
End Sub  
```  
  
##  <a name="BKMK_Example"></a> Vollständiges Beispiel  
 Das nächste Windows Presentation Foundation (WPF)-Projekt enthält die Codebeispiele aus diesem Thema.  
  
 Um das Projekt auszuführen, führen Sie die folgenden Schritte aus:  
  
1.  Starten Sie Visual Studio.  
  
2.  Wählen Sie in der Menüleiste **Datei**, **Neu**, **Projekt**aus.  
  
     Das Dialogfeld **Neues Projekt** wird angezeigt.  
  
3.  In der **installiert**, **Vorlagen** Kategorie wählen **Visual Basic**, und wählen Sie dann **Windows**. Wählen Sie in der Liste der Projekttypen die **WPF-Anwendung** aus.  
  
4.  Geben Sie `AsyncReturnTypes` als Namen für das Projekt ein, und wählen Sie dann die Schaltfläche **OK** aus.  
  
     Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.  
  
5.  Wählen Sie im Visual Studio Code Editor die Registerkarte **MainWindow.xaml** aus.  
  
     Wenn die Registerkarte nicht sichtbar ist, öffnen Sie das Kontextmenü für „MainWindow.xaml“ im **Projektmappen-Explorer** und wählen dann **Öffnen** aus.  
  
6.  Ersetzen Sie den Code im Fenster **XAML** von „MainWindow.xaml“ durch den folgenden Code.  
  
    ```vb  
    <Window x:Class="MainWindow"  
            xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
            xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
            Title="MainWindow" Height="350" Width="525">  
        <Grid>  
            <Button x:Name="button1" Content="Start" HorizontalAlignment="Left" Margin="214,28,0,0" VerticalAlignment="Top" Width="75" HorizontalContentAlignment="Center" FontWeight="Bold" FontFamily="Aharoni" Click="button1_Click"/>  
            <TextBox x:Name="textBox1" Margin="0,80,0,0" TextWrapping="Wrap" FontFamily="Lucida Console"/>  
  
        </Grid>  
    </Window>  
    ```  
  
     Ein einfaches Fenster mit einem Textfeld und einer Schaltfläche wird im Fenster **Entwurf** von „MainWindow.xaml“ angezeigt.  
  
7.  In **Projektmappen-Explorer**, öffnen Sie das Kontextmenü für "MainWindow.Xaml.vb", und wählen Sie dann **Ansichtscode**.  
  
8.  Ersetzen Sie den Code in „MainWindow.xaml.vb“ durch den folgenden Code.  
  
    ```vb  
    Class MainWindow  
  
        ' SUB EXAMPLE  
        Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
  
            textBox1.Clear()  
  
            ' Start the process and await its completion. DriverAsync is a   
            ' Task-returning async method.  
            Await DriverAsync()  
  
            ' Say goodbye.  
            textBox1.Text &= vbCrLf & "All done, exiting button-click event handler."  
        End Sub  
  
        Async Function DriverAsync() As Task  
  
            ' Task(Of T)   
            ' Call and await the Task(Of T)-returning async method in the same statement.  
            Dim result1 As Integer = Await TaskOfT_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim integerTask As Task(Of Integer) = TaskOfT_MethodAsync()  
  
            ' You can do other work that does not rely on resultTask before awaiting.  
            textBox1.Text &= String.Format("Application can continue working while the Task(Of T) runs. . . . " & vbCrLf)  
  
            Dim result2 As Integer = Await integerTask  
  
            ' Display the values of the result1 variable, the result2 variable, and  
            ' the resultTask.Result property.  
            textBox1.Text &= String.Format(vbCrLf & "Value of result1 variable:   {0}" & vbCrLf, result1)  
            textBox1.Text &= String.Format("Value of result2 variable:   {0}" & vbCrLf, result2)  
            textBox1.Text &= String.Format("Value of resultTask.Result:  {0}" & vbCrLf, integerTask.Result)  
  
            ' Task   
            ' Call and await the Task-returning async method in the same statement.  
            Await Task_MethodAsync()  
  
            ' Call and await in separate statements.  
            Dim simpleTask As Task = Task_MethodAsync()  
  
            ' You can do other work that does not rely on simpleTask before awaiting.  
            textBox1.Text &= String.Format(vbCrLf & "Application can continue working while the Task runs. . . ." & vbCrLf)  
  
            Await simpleTask  
        End Function  
  
        ' TASK(OF T) EXAMPLE  
        Async Function TaskOfT_MethodAsync() As Task(Of Integer)  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.FromResult is a placeholder for actual work that returns a string.  
            Dim today As String = Await Task.FromResult(Of String)(DateTime.Now.DayOfWeek.ToString())  
  
            ' The method then can process the result in some way.  
            Dim leisureHours As Integer  
            If today.First() = "S" Then  
                leisureHours = 16  
            Else  
                leisureHours = 5  
            End If  
  
            ' Because the return statement specifies an operand of type Integer, the   
            ' method must have a return type of Task(Of Integer).   
            Return leisureHours  
        End Function  
  
        ' TASK EXAMPLE  
        Async Function Task_MethodAsync() As Task  
  
            ' The body of an async method is expected to contain an awaited   
            ' asynchronous call.  
            ' Task.Delay is a placeholder for actual work.  
            Await Task.Delay(2000)  
            textBox1.Text &= String.Format(vbCrLf & "Sorry for the delay. . . ." & vbCrLf)  
  
            ' This method has no return statement, so its return type is Task.   
        End Function  
  
    End Class  
    ```  
  
9. Drücken Sie die Taste F5, um das Programm auszuführen, und klicken Sie dann auf die Schaltfläche **Starten** .  
  
     Es sollte folgende Ausgabe angezeigt werden.  
  
    ```  
    Application can continue working while the Task<T> runs. . . .   
  
    Value of result1 variable:   5  
    Value of result2 variable:   5  
    Value of integerTask.Result: 5  
  
    Sorry for the delay. . . .  
  
    Application can continue working while the Task runs. . . .  
  
    Sorry for the delay. . . .  
  
    All done, exiting button-click event handler.  
    ```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Threading.Tasks.Task.FromResult%2A>
- [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Ablaufsteuerung in asynchronen Programmen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)
- [Async](../../../../visual-basic/language-reference/modifiers/async.md)
- [Await-Operator](../../../../visual-basic/language-reference/operators/await-operator.md)
