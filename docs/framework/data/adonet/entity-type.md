---
title: Entitätstyp
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 3955de1873d80e85df713a557750e34e76efeb41
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502883"
---
# <a name="entity-type"></a>Entitätstyp
Die *Entitätstyp* ist der wesentliche Baustein zum Beschreiben der Datenstruktur mit dem Entity Data Model (EDM). In einem konzeptionellen Modell stellt ein Entitätstyp die Struktur von Konzepten der obersten Ebene dar, z. B. Kunden oder Bestellungen. Ein Entitätstyp ist eine Vorlage für Entitätstypinstanzen. Jede Vorlage enthält die folgenden Informationen:  
  
-   Eine eindeutige Bezeichnung. (Erforderlich.)  
  
-   Ein [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) durch eine oder mehrere Eigenschaften definiert. (Erforderlich.)  
  
-   Daten in Form von [Eigenschaften](../../../../docs/framework/data/adonet/property.md). (Optional)  
  
-   [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) , mit denen für die Navigation von einem [End](../../../../docs/framework/data/adonet/association-end.md) von einem [Zuordnung](../../../../docs/framework/data/adonet/association-type.md) zum anderen Ende. (Optional)  
  
 In einer Anwendung stellt eine Instanz eines Entitätstyps ein spezielles Objekt dar, wie etwa einen bestimmten Kunden oder eine Bestellung. Jede Instanz eines Entitätstyps muss eine eindeutige verfügen [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) innerhalb einer [Entitätenmenge](../../../../docs/framework/data/adonet/entity-set.md).  
  
 Zwei Instanzen eines Entitätstyps werden nur dann als gleich betrachtet, wenn sie vom selben Typ sind und die Werte ihrer Entitätsschlüssel übereinstimmen.  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`:  
  
 ![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Beachten Sie, dass die Eigenschaften jedes Entitätstyps, die den entsprechenden Entitätsschlüssel bilden, mit "(Schlüssel)" angegeben werden.  
  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren. Die folgende CSDL definiert den in der Abbildung oben gezeigten `Book`-Entitätstyp:  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>Siehe auch
- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
- [facet](../../../../docs/framework/data/adonet/facet.md)
