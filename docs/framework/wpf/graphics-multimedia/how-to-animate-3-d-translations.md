---
title: 'Vorgehensweise: Animieren von 3D-Übersetzungen'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], 3-D translations
- 3-D translations [WPF], animating
ms.assetid: d4eece1f-0cd2-4a2c-8370-293354c380e4
ms.openlocfilehash: e73035a48e32e3eec20b44c82b5b9ec6763c1e7c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54653033"
---
# <a name="how-to-animate-3-d-translations"></a>Vorgehensweise: Animieren von 3D-Übersetzungen
In diesem Thema wird veranschaulicht, wie eine Übersetzungsumwandlung, legen Sie für animiert ein [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] Modell.  
  
 Der folgende Code zeigt die Anwendung von einer <xref:System.Windows.Media.Media3D.TranslateTransform3D> -Objekt an die <xref:System.Windows.Media.Media3D.Model3D.Transform%2A> Eigenschaft eine <xref:System.Windows.Media.Media3D.GeometryModel3D>.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline1)]  
  
 Die <xref:System.Windows.Media.Media3D.TranslateTransform3D.OffsetX%2A> -Eigenschaft dieses <xref:System.Windows.Media.Media3D.TranslateTransform3D> Objekt animiert wird, mit dem folgenden Code.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationInline2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationinline2)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das gesamte Beispiel.  
  
 [!code-xaml[Animation3DGallery_snip#Translation3DAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/Translation3DAnimationExample.xaml#translation3danimationexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch
- [Übersicht über Animationen](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Erstellen einer 3D-Szene](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)
- [Übersicht über 3D-Grafiken](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
- [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
