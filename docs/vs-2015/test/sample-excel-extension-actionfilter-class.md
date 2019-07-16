---
title: 'Ukázka rozšíření Excel: Třída ActionFilter | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
ms.assetid: c69fe3c7-f797-4e90-b21c-f2cc4dddf152
caps.latest.revision: 13
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 86c1dda46ed0e62649a576a12c9f9e48561ec891
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68158167"
---
# <a name="sample-excel-extension-actionfilter-class"></a>Ukázka rozšíření Excel: Třída ActionFilter
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tento vnitřní třída rozšiřuje <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> třídy a představuje filtr testovacích akcí na [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] elementu.  
  
## <a name="simple-properties"></a>Jednoduché vlastnosti  
 Tyto vlastnosti jen pro čtení umožňují vývojářům určit, jak tento filtr akce testu má být provedena v rámci programových rozhraní testování uživatelského rozhraní. Například <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A> vlastnosti obsahuje název filtru akce. Další vlastnosti get <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A> filtru akce <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> název akce testu, které jsou filtrovány podle filtru akce tohoto testu. Ostatní označuje, jestli se má <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A> a také, jestli je akce testu <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A>.  
  
## <a name="processrule-method"></a>ProcessRule – metoda  
 Tato metoda je volána metodou testovací rozhraní programového uživatelského rozhraní a spouští filtr proti poskytnuté <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>. Toto konkrétní přepsání odebere myši vybrat akci na buňky při další akce v zásobníku odešle stisknutí kláves do buňky. Potom vrátí `false`.  
  
## <a name="private-methods"></a>Privátní metody  
 `IsLeftClick` Metody Určuje, zda zadaná akce představuje přejít myši. `AreActionsOnSameExcelCell` Metoda určuje, zda dva zadané akce jsou spouštěny na stejné buňky v aplikaci Excel.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>   
 [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
