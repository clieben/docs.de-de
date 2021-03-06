---
title: 'Vorgehensweise: Programmgesteuertes Hinzufügen von Elementen zu DomainUpDown-Steuerelementen für Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 865f569da561ec5883b0a0f08fcedb34fc84820c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54738559"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>Vorgehensweise: Programmgesteuertes Hinzufügen von Elementen zu DomainUpDown-Steuerelementen für Windows Forms
Sie können Elemente hinzufügen, auf die Windows-Formulare <xref:System.Windows.Forms.DomainUpDown> Steuerelement im Code. Rufen Sie die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> oder <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> Methode der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> Klasse, um die Elemente des Steuerelements hinzufügen <xref:System.Windows.Forms.DomainUpDown.Items%2A> Eigenschaft. Die <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> Methode fügt ein Element am Ende einer Auflistung während der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> Methode fügt ein Element an einer angegebenen Position.  
  
### <a name="to-add-a-new-item"></a>Um ein neues Element hinzufügen  
  
1.  Verwenden der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> Methode, um ein Element am Ende der Liste der Elemente hinzuzufügen.  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     - oder -   
  
2.  Verwenden der <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> Methode zum Einfügen eines Elements in der Liste an einer angegebenen Position.  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [DomainUpDown-Steuerelement](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)
- [Übersicht über das DomainUpDown-Steuerelement](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
