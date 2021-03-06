---
title: 'Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu Freihanddaten'
ms.date: 03/30/2017
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
ms.openlocfilehash: 40d883f3d3e1d504c8757c31325aa72a03da37e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544510"
---
# <a name="how-to-add-custom-data-to-ink-data"></a>Gewusst wie: Hinzufügen von benutzerdefinierten Daten zu Freihanddaten
Sie können benutzerdefinierte Daten Freihandeingaben hinzufügen, die zusammen die Freihandeingabe als serialisiert Freihand-Format (ISF) gespeichert.  Sie können die benutzerdefinierten Daten zu speichern die <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection>, oder die <xref:System.Windows.Ink.Stroke>.  Die Möglichkeit zum Speichern von benutzerdefinierter Daten für drei Objekte bietet Ihnen die Möglichkeit, um zu entscheiden, die beste Möglichkeit zum Speichern der Daten.  Alle drei Klassen verwenden ähnliche Methoden zum Speichern und Zugreifen auf benutzerdefinierte Daten an.  
  
 Nur die folgenden Typen können als benutzerdefinierte Daten gespeichert werden:  
  
-   <xref:System.Boolean>  
  
-   <xref:System.Boolean>[]  
  
-   <xref:System.Byte>  
  
-   <xref:System.Byte>[]  
  
-   <xref:System.Char>  
  
-   <xref:System.Char>[]  
  
-   <xref:System.DateTime>  
  
-   <xref:System.DateTime>[]  
  
-   <xref:System.Decimal>  
  
-   <xref:System.Decimal>[]  
  
-   <xref:System.Double>  
  
-   <xref:System.Double>[]  
  
-   <xref:System.Int16>  
  
-   <xref:System.Int16>[]  
  
-   <xref:System.Int32>  
  
-   <xref:System.Int32>[]  
  
-   <xref:System.Int64>  
  
-   <xref:System.Int64>[]  
  
-   <xref:System.Single>  
  
-   <xref:System.Single>[]  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <xref:System.UInt16>[]  
  
-   <xref:System.UInt32>  
  
-   <xref:System.UInt32>[]  
  
-   <xref:System.UInt64>  
  
-   <xref:System.UInt64>[]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Hinzufügen und Abrufen von benutzerdefinierten Daten aus einer <xref:System.Windows.Ink.StrokeCollection>.  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 Das folgende Beispiel erstellt eine Anwendung, die zeigt eine <xref:System.Windows.Controls.InkCanvas> und zwei Schaltflächen.  Die Schaltfläche `switchAuthor`, zwei Stifte, die von zwei verschiedenen Autoren verwendet werden können.  Die Schaltfläche mit den `changePenColors` ändert sich die Farbe jedes Strich auf die <xref:System.Windows.Controls.InkCanvas> gemäß den Autor.  Die Anwendung definiert zwei <xref:System.Windows.Ink.DrawingAttributes> -Objekte und fügt eine benutzerdefinierte Eigenschaft für jede Anwendung, der angibt, welche Autor gezeichnet wurde die <xref:System.Windows.Ink.Stroke>.  Wenn der Benutzer klickt `changePenColors`, die Anwendung ändert die Darstellung des Strichs entsprechend dem Wert der benutzerdefinierten Eigenschaft.  
  
 [!code-xaml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
