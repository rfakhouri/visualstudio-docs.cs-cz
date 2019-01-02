---
title: Přístup k textu vrstvy pomocí starší verze rozhraní API | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - text layers
ms.assetid: 2258fcdd-38d1-479d-b8f8-1d4e6525f72c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 47085216c6f20ca1add535a76ce4f5fb4043a6dd
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53945935"
---
# <a name="access-text-layers-by-using-the-legacy-api"></a>Vrstvy přístupu k textu pomocí starší verze rozhraní API
Text vrstva obvykle zapouzdřuje určitý aspekt rozložení textu. Například vrstva "funkce na-time" Skryje text před a za funkci obsahující znak stříšky (textový kurzor).  
  
 Text vrstvě se nachází mezi vyrovnávací paměť a zobrazení a mění způsob zobrazení se zobrazí obsah přípravné vyrovnávací paměti.  
  
## <a name="text-layer-information"></a>Informace o vrstvě textu  
 Následující seznam popisuje, jak fungují text vrstvy [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]:  
  
-   Text ve vrstvě text můžete opatřený s barevné zvýrazňování syntaxe a značky.  
  
-   Momentálně nelze implementovat vlastní vrstvy.  
  
-   Poskytuje vrstvu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>, který je odvozen z <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>. Samotné vyrovnávací paměti textu je také implementováno jako vrstvu, která umožňuje zobrazení řešit polymorphically vrstvách.  
  
-   Libovolný počet vrstvy můžou být mezi zobrazením a vyrovnávací paměti. Každá vrstva se zabývá pouze vrstvy pod ní a zobrazení se zabývá do značné míry vrstvě úplně nahoře. (Zobrazení má některé informace o vyrovnávací paměti.)  
  
-   Vrstva může mít vliv pouze vrstvy, které jsou pod ním. Ho nemůže ovlivnit vrstvy nad ním nad rámec standardních události pocházející.  
  
-   V editoru skrytý text, syntetické a zalamování řádků jsou implementovány jako vrstvy. Skryté a syntetické text můžete implementovat bez práci přímo s vrstvami. Další informace najdete v tématu [osnovy ve službě starší verze jazyka](../extensibility/internals/outlining-in-a-legacy-language-service.md) a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSyntheticTextSession>.  
  
-   Každá vrstva text má vlastní místní systém souřadnic, který je zveřejněný prostřednictvím <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer> rozhraní. Zalamování řádků vrstvy, například může obsahovat dva řádky během základní textové vyrovnávací paměti může obsahovat pouze jeden řádek.  
  
-   Zobrazení komunikuje s vrstvami prostřednictvím <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView> rozhraní. Pomocí tohoto rozhraní sjednotit zobrazení souřadnic s vyrovnávací paměť souřadnic.  
  
-   Žádné vrstvy, jako je vrstva syntetické text, který pochází text musí poskytnout implementaci místní <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CreateTrackingPoint%2A>.  
  
-   Kromě <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>, musí implementovat vrstvu text <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> a aktivovat události v <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents> rozhraní.  
  
## <a name="see-also"></a>Viz také:  
 [Barevné zvýrazňování syntaxe ve vlastních editorech](../extensibility/syntax-coloring-in-custom-editors.md)   
 [Text značky pomocí starší verze rozhraní API](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Přizpůsobení nabídky a ovládací prvky editoru pomocí starší verze rozhraní API](../extensibility/customizing-editor-controls-and-menus-by-using-the-legacy-api.md)