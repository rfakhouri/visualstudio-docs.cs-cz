---
title: "Přístup k vrstvy textu s použitím rozhraní API starší | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - text layers
ms.assetid: 2258fcdd-38d1-479d-b8f8-1d4e6525f72c
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 54a981a57605ccb93062ac0678b1e8b5673c6d1a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="accessing-text-layers-by-using-the-legacy-api"></a>Přístup k vrstvy textu s použitím rozhraní API starší verze
Vrstva text obvykle zapouzdří některých aspektů rozložení textu. Například "funkce na čas" vrstvu skryje text před a po funkci obsahující pomocí kurzoru (bod vložení textu).  
  
 Vrstva textu se nachází mezi vyrovnávací paměť a zobrazení a upravuje způsob zobrazení se zobrazí obsah do vyrovnávací paměti.  
  
## <a name="text-layer-information"></a>Informace o vrstvy textu  
 Následující seznam popisuje, jak fungují vrstvy textu v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]:  
  
-   Text ve vrstvě text můžete ozdobené s značky a barevné zvýrazňování syntaxe.  
  
-   Momentálně nelze implementovat vlastní vrstvy.  
  
-   Vrstva zpřístupní <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>, který je odvozen z <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLines>. Samotný textová vyrovnávací paměť je také implementovaný jako vrstvu, která umožňuje zobrazení řešení polymorphically základní vrstvy.  
  
-   Libovolný počet vrstev může být mezi zobrazení a vyrovnávací paměť. Každý úroveň pracuje pouze s vrstvou pod ní a zobrazení, je z velké části zabývá nejvyšší vrstvy. (Zobrazení mají některé informace o vyrovnávací paměti.)  
  
-   Vrstva může ovlivnit pouze vrstvy, které jsou pod ním. To nelze ovlivnit vrstvy nad ním nad rámec pocházející standardních událostí.  
  
-   V editoru skrytého textu, syntetické text a zalamování řádků se implementují jako vrstvy. Skryté a syntetické text můžete implementovat bez interakcí s vrstvy. Další informace najdete v tématu [osnovy ve službě jazyk starší](../extensibility/internals/outlining-in-a-legacy-language-service.md) a <xref:Microsoft.VisualStudio.TextManager.Interop.IVsSyntheticTextSession>.  
  
-   Jednotlivé úrovně text má svůj vlastní místní systém souřadnic, který je zveřejněný prostřednictvím <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer> rozhraní. Zalamování řádků vrstvy, například může obsahovat dva řádky při základní textová vyrovnávací paměť může obsahovat pouze jednu čáru.  
  
-   Zobrazení komunikuje s vrstvami prostřednictvím <xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView> rozhraní. Pomocí tohoto rozhraní sjednotit souřadnice zobrazení s souřadnice vyrovnávací paměti.  
  
-   Všechny vrstvy, jako je vrstvě syntetické textu, který pochází text musíte zadat místní provádění <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer.CreateTrackingPoint%2A>.  
  
-   Kromě <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLayer>, musí implementovat vrstva text <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> a vyvolání události v <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextLinesEvents> rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Vlastní editorů zvýrazňování syntaxe](../extensibility/syntax-coloring-in-custom-editors.md)   
 [Text značky pomocí starší verze rozhraní API](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [Přizpůsobení ovládací prvky editoru a nabídky pomocí starší verze rozhraní API](../extensibility/customizing-editor-controls-and-menus-by-using-the-legacy-api.md)