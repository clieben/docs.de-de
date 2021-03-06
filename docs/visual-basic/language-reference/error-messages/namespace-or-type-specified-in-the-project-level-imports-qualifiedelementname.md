---
title: Der in Imports '<qualifiedelementname>' auf Projektebene angegebene Namespace oder Typ enthält keine öffentlichen Member oder kann nicht gefunden werden
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: 12d20a88179a3d0c93c18f0aed65ca46b001059a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283308"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a>Namespace oder Typ angegeben werden, in das Projekt auf Dokumentebene Imports'\<qualifizierter_elementname >' enthält keine öffentlichen Member oder wurde nicht gefunden
Namespace oder Typ angegeben werden, in das Projekt auf Dokumentebene Imports'\<qualifizierter_elementname >' enthält keine öffentlichen Member oder wurde nicht gefunden. Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentliches Member enthält. Stellen Sie sicher, dass der Aliasname keine andere Aliase enthält.  
  
 Eine Import-Eigenschaft eines Projekts gibt ein enthaltendes Element, das entweder nicht gefunden werden kann, oder keine definiert `Public` Member.  
  
 Ein *, das Element enthält* -Namespace, Klasse, Struktur, Modul, Schnittstelle oder Enumeration sein kann. Das enthaltende Element enthält Member, z. B. Variablen, Prozeduren oder andere Elemente enthält.  
  
 Importieren von dient zu Ihrem Code, um Namespaces oder Typs auf Member zuzugreifen, ohne sie zu qualifizieren. Ihr Projekt müssen möglicherweise auch einen Verweis auf den Namespace oder Typ hinzufügen. Weitere Informationen finden Sie unter "Importieren von enthaltenen Elementen" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
 Wenn der Compiler das angegebene Element enthält, nicht finden kann, und klicken Sie dann nicht Verweise aufgelöst werden kann, die sie verwenden. Wenn das Element gefunden wird, das Element macht aber keine `Public` Elemente, und klicken Sie dann auf keinen Verweis kann erfolgreich sein. In beiden Fällen ist es ohne Bedeutung für das Element zu importieren.  
  
 Sie verwenden die **Projekt-Designer** zu importierenden Elemente angeben. Verwenden der **importierte Namespaces** Teil der **Verweise** Seite. Erhalten Sie auf die **Projekt-Designer** durch Doppelklicken auf die **Mein Projekt** Symbol **Projektmappen-Explorer**.  
  
 **Fehler-ID:** BC40057  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Öffnen der **Projekt-Designer** und wechseln Sie zu der **Verweis** Seite.  
  
2.  In der **importierte Namespaces** Abschnitt, stellen Sie sicher, dass das enthaltende Element aus Ihrem Projekt möglich ist.  
  
3.  Stellen Sie sicher, dass das enthaltende Element verfügbar, mindestens eine macht `Public` Member.  
  
## <a name="see-also"></a>Siehe auch
- [Seite „Verweise“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
- [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
