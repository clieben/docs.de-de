---
title: <list> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: 522450e4efcecaf74968ddb492b536aa98dc0b13
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260289"
---
# <a name="list-visual-basic"></a>\<list> (Visual Basic)
Definiert eine Liste oder Tabelle.  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
#### <a name="parameters"></a>Parameter  
 `type`  
 Der Typ der Liste. Muss eine "Bullet" für eine Liste mit Aufzählungszeichen, "Number" für eine nummerierte Liste oder "Table" für eine Tabelle mit zwei Spalten.  
  
 `term`  
 Nur verwendet, wenn `type` ist "table". Ein zu definierender Begriff, die in der Beschreibungstag definiert ist.  
  
 `description`  
 Wenn `type` ist "Bullet" oder "number", `description` ist ein Element in der Liste bei `type` ist "table" `description` ist die Definition der `term`.  
  
## <a name="remarks"></a>Hinweise  
 Die `<listheader>` -Block definiert die Überschrift einer Tabelle oder einer Definition. Wenn Sie eine Tabelle zu definieren, Sie müssen nur ein Eintrag für angegeben `term` in der Überschrift.  
  
 Jedes Element in der Liste wird angegeben, mit einem `<item>` Block. Beim Erstellen einer Definitionsliste müssen Sie angeben, beide `term` und `description`. Allerdings für eine Tabelle, Liste mit Aufzählungszeichen oder nummerierte Liste, Sie müssen nur ein Eintrag für angegeben `description`.  
  
 Eine Liste oder Tabelle lassen sich so viele `<item>` blockiert nach Bedarf.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `<list>` Tag, um eine Liste mit Aufzählungszeichen im Abschnitt "Hinweise" definieren.  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/index.md)
