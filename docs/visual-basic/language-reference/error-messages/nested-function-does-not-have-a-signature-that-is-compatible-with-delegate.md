---
title: Die geschachtelte Funktion verfügt über keine Signatur, die mit dem Delegaten '<delegatename>' kompatibel ist
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: ea6f230715520cb35809d57db76b300da326ec9a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283464"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a>Geschachtelte Funktion verfügt nicht über eine Signatur, mit dem Delegaten kompatibel ist "\<Delegatname >'
Ein Lambda-Ausdruck wurde in einen Delegaten zugewiesen, die über eine nicht kompatible Signatur verfügt. Im folgenden Code wird z. B. Delegieren `Del` verfügt über zwei ganzzahlige Parameter.  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 Der Fehler wird ausgelöst, wenn ein Lambda-Ausdruck mit einem Argument als Typ deklariert wird `Del`:  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **Fehler-ID:** BC36532  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Passen Sie entweder die Delegatdefinition oder den zugewiesenen Lambda-Ausdruck, sodass die Signaturen kompatibel sind.  
  
## <a name="see-also"></a>Siehe auch
- [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
