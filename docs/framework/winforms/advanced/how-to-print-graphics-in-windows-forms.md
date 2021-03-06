---
title: 'Vorgehensweise: Drucken von Grafiken in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: db83d03d38acebfe42d383efdb2caa550bc2013a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54636104"
---
# <a name="how-to-print-graphics-in-windows-forms"></a>Vorgehensweise: Drucken von Grafiken in Windows Forms
In vielen Fällen möchten Sie Drucken von Grafiken in Ihrer Windows-basierten Anwendung. Die <xref:System.Drawing.Graphics> -Klasse stellt Methoden zum Zeichnen von Objekten auf einem Gerät, z. B. einem Bildschirm oder Drucker.  
  
### <a name="to-print-graphics"></a>Zum Drucken von Grafiken  
  
1.  Hinzufügen einer <xref:System.Drawing.Printing.PrintDocument> Ihrem Formular.  
  
2.  In der <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignishandler der <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs> Klasse an den Drucker auf welche Art von zu druckenden Grafiken.  
  
     Das folgende Codebeispiel zeigt einen Ereignishandler verwendet, um eine blaue Ellipse in ein umschließendes Rechteck zu erstellen. Das Rechteck hat den folgenden Speicherort und Dimensionen: beginnend bei 100, 150 mit einer Breite von 250 und eine Höhe von 250.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     (Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
