---
title: Sicherheit und schreibgeschützte öffentliche Arrayfelder
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03f3ce51eaab9e08d5f05932d9360adc4fd2110f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560986"
---
# <a name="security-and-public-read-only-array-fields"></a>Sicherheit und schreibgeschützte öffentliche Arrayfelder
Verwenden Sie niemals schreibgeschützte öffentliche Arrayfelder aus verwalteten Bibliotheken, die Verhalten oder die Sicherheit Ihrer Anwendungen zu definieren, da schreibgeschützte öffentliche Arrayfelder geändert werden können.  
  
## <a name="remarks"></a>Hinweise  
 Einige .NET Framework-Klassen sind schreibgeschützte öffentliche Felder, die plattformspezifische Grenzen-Parameter enthalten.  Z. B. die <xref:System.IO.Path.InvalidPathChars> Feld ist ein Array, das die Zeichen beschreibt, die nicht in einer Pfadzeichenfolge Datei zulässig sind.  Viele ähnliche Felder, die in .NET Framework vorhanden sind.  
  
 Die Werte der öffentliche schreibgeschützte Felder wie <xref:System.IO.Path.InvalidPathChars> kann geändert werden, von Ihrem Code oder Code, der in derselben Anwendungsdomäne Ihres Codes verwendet.  Sie sollten nicht schreibgeschützte öffentliche Arrayfelder wie folgt verwenden, um das Verhalten Ihrer Anwendungen zu definieren.  Wenn Sie dies tun, kann schädlichen Code die Grenzdefinitionen alter und verwenden Ihren Code auf unerwartete Weise.  
  
 In Version 2.0 oder höher von .NET Framework sollten Sie Methoden verwenden, die ein neues Array, statt öffentliche Arrayfelder zurückgeben.  Z. B. statt der <xref:System.IO.Path.InvalidPathChars> Feld, verwenden Sie die <xref:System.IO.Path.GetInvalidPathChars%2A> Methode.  
  
 Beachten Sie, die .NET Framework-Typen nicht öffentlichen Felder verwenden, um grenztypen intern zu definieren.  Stattdessen verwendet das .NET Framework separate private Felder.  Ändern Sie die Werte dieser öffentlichen Felder wird das Verhalten der .NET Framework-Typen nicht geändert werden.  
  
## <a name="see-also"></a>Siehe auch
- [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
