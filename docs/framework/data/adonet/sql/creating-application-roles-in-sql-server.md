---
title: Erstellen von Anwendungsrollen in SQL Server
ms.date: 03/30/2017
ms.assetid: 27442435-dfb2-4062-8c59-e2960833a638
ms.openlocfilehash: 4d3ee759a11417d5f4d36a295f20c7f7886d30d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54638131"
---
# <a name="creating-application-roles-in-sql-server"></a>Erstellen von Anwendungsrollen in SQL Server
Anwendungsrollen bieten die Möglichkeit, einer Anwendung anstelle von Datenbankrollen oder Benutzern Berechtigungen zuzuweisen. Benutzer können eine Verbindung mit der Datenbank herstellen, die Anwendungsrolle aktivieren und die der Anwendung erteilten Berechtigungen annehmen. Die der Anwendungsrolle gewährten Berechtigungen sind so lange in Kraft, wie die Verbindung besteht.  
  
> [!IMPORTANT]
>  Anwendungsrollen werden aktiviert, wenn eine Clientanwendung in der Verbindungszeichenfolge einen Anwendungsrollennamen und ein Kennwort bereitstellt. In 2-Ebenen-Anwendungen stellen Anwendungsrollen ein Sicherheitsrisiko dar, weil das Kennwort auf dem Clientcomputer gespeichert werden muss. In 3-Ebenen-Anwendungen können Sie das Kennwort so speichern, dass die Benutzer der Anwendung nicht darauf zugreifen können.  
  
## <a name="application-role-features"></a>Funktionen der Anwendungsrollen  
 Anwendungsrollen weisen die folgenden Funktionen auf:  
  
-   Im Unterschied zu Datenbankrollen enthalten Anwendungsrollen keine Member.  
  
-   Anwendungsrollen werden aktiviert, wenn eine Anwendung der gespeicherten Systemprozedur `sp_setapprole` einen Anwendungsrollennamen und ein Kennwort bereitstellt.  
  
-   Das Kennwort muss auf dem Clientcomputer gespeichert und zur Laufzeit bereitgestellt werden. Die Aktivierung der Anwendungsrolle von SQL Server aus ist nicht möglich.  
  
-   Das Kennwort wird nicht verschlüsselt. Das Parameterkennwort wird als unidirektionaler Hash gespeichert.  
  
-   Einmal aktiviert, bleiben durch die Anwendungsrolle abgerufene Berechtigungen für die gesamte Dauer der Verbindung wirksam.  
  
-   Die Anwendungsrolle erbt die der Rolle `public` gewährten Berechtigungen.  
  
-   Wenn ein Member der festen Serverrolle `sysadmin` eine Anwendungsrolle aktiviert, wechselt der Sicherheitskontext für die Dauer der Verbindung zum Sicherheitskontext der Anwendungsrolle.  
  
-   Wenn Sie in einer Datenbank ein `guest`-Konto erstellen, das eine Anwendungsrolle besitzt, müssen Sie kein Datenbankbenutzerkonto für die Anwendungsrolle oder für eine der Anmeldungen erstellen, die die Rolle aufrufen. Anwendungsrollen können auf eine andere Datenbank nur direkt zugreifen, wenn in dieser anderen Datenbank ein `guest`-Konto vorhanden ist.  
  
-   Integrierte Funktionen, die Anmeldenamen, z. B. SYSTEM_USER, zurückgeben, geben den Namen der Anmeldung zurück, die die Anwendungsrolle aufgerufen hat. Integrierte Funktionen, die Datenbankbenutzernamen zurückgeben, geben den Namen der Anwendungsrolle zurück.  
  
### <a name="the-principle-of-least-privilege"></a>Das Prinzip der minimalen Rechtegewährung  
 Anwendungsrollen sollten immer nur die unbedingt notwendigen Berechtigungen gewährt werden, um so für den Fall vorzusorgen, dass das Kennwort in die falschen Hände gerät. Berechtigungen für die Rolle `public` sollten in allen Datenbanken, die eine Anwendungsrolle verwenden, widerrufen werden. Deaktivieren Sie das `guest`-Konto in allen Datenbanken, auf die Inhaber der Anwendungsrolle keinen Zugriff haben sollen.  
  
### <a name="application-role-enhancements"></a>Verbesserungen bei den Anwendungsrollen  
 Der Ausführungskontext kann wieder zum ursprünglichen Aufrufer zurückwechseln, nachdem eine Anwendungsrolle aktiviert wurde, sodass das Verbindungspooling nicht deaktiviert werden muss. Die `sp_setapprole`-Prozedur verfügt über eine neue Option, die ein Cookie erstellt, das Kontextinformationen zum Aufrufer enthält. Sie können die Sitzung wiederherstellen, indem Sie die `sp_unsetapprole`-Prozedur aufrufen und ihr das Cookie übergeben.  
  
## <a name="application-role-alternatives"></a>Alternativen zu Anwendungsrollen  
 Anwendungsrollen sind von der Sicherheit eines Kennworts abhängig und stellen so ein potenzielles Sicherheitsrisiko dar. Kennwörter, die in den Anwendungscode eingebettet sind oder auf der Festplatte gespeichert werden, können leicht ausspioniert werden.  
  
 Sie sollten die folgenden Alternativen in Erwägung ziehen.  
  
-   Verwenden Sie Kontextwechsel mit der EXECUTE AS-Anweisung und deren Klauseln NO REVERT und WITH COOKIE. Sie können ein Benutzerkonto in einer Datenbank erstellen, das keiner Anmeldung zugeordnet ist. Anschließend weisen Sie diesem Konto Berechtigungen zu. Die Verwendung von EXECUTE AS mit einem <legacyBold>login-less</legacyBold>-Benutzer ist sicherer, da sie auf Berechtigungen und nicht auf dem Kennwort basiert. Weitere Informationen finden Sie unter [Anpassen von Berechtigungen durch Identitätswechsel in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md).  
  
-   Signieren Sie gespeicherte Prozeduren mit Zertifikaten, die nur die Berechtigung gewähren, die zum Ausführen der Prozeduren notwendig ist. Weitere Informationen finden Sie unter [Signieren von gespeicherten Prozeduren in SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md).  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Anwendungsrollen](/sql/relational-databases/security/authentication-access/application-roles)|Beschreibt das Erstellen und Verwenden von Anwendungsrollen in SQL Server 2008.|  
  
## <a name="see-also"></a>Siehe auch
- [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)
- [Übersicht über die SQL Server-Sicherheit](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)
- [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
