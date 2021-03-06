---
title: Spät gebundene Auflösung. Laufzeitfehler sind möglich.
ms.date: 07/20/2015
f1_keywords:
- vbc42017
- BC42017
helpviewer_keywords:
- BC42017
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
ms.openlocfilehash: 9caf02907e4b6de4c2bd8de778d4ad7a9320a82b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54690578"
---
# <a name="late-bound-resolution-runtime-errors-could-occur"></a>Spät gebundene Auflösung. Laufzeitfehler sind möglich.
Ein Objekt erhält, eine Variable deklariert die [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md).  
  
 Wenn Sie eine Variable deklarieren `Object`, muss der Compiler eine *späte Bindung*, die zur Laufzeit zusätzliche Vorgänge verursacht. Sie setzt die Anwendung zudem möglichen Laufzeitfehlern aus. Angenommen, Sie weisen eine <xref:System.Windows.Forms.Form> zu der `Object` Variable, und wiederholen Sie dann auf die <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=nameWithType> -Eigenschaft, löst die Laufzeit eine <xref:System.MemberAccessException> da die <xref:System.Windows.Forms.Form> -Klasse macht keinen verfügbar eine `NameTable` Eigenschaft.  
  
 Wenn Sie die Variable einen bestimmten Typ deklarieren, kann der Compiler führen *frühe Bindung* zum Zeitpunkt der Kompilierung. Dies führt zu einer Verbesserung der Leistung kontrollierten Zugriff auf die Elemente des angegebenen Typs und einer besseren Lesbarkeit Ihres Codes.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42017  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn möglich, deklarieren Sie die Variable eines bestimmten Typs sein.  
  
## <a name="see-also"></a>Siehe auch
- [Frühes und spätes Binden](../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [Deklaration von Objektvariablen](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
