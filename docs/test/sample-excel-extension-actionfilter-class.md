---
title: "Ukázka rozšíření aplikace Excel: Třída Actionfilter | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c69fe3c7-f797-4e90-b21c-f2cc4dddf152
caps.latest.revision: "11"
ms.author: douge
manager: douge
ms.openlocfilehash: 346cb9faddf2bd155c91d9fc72176020ba43197b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="sample-excel-extension-actionfilter-class"></a>Ukázka rozšíření aplikace Excel: třída ActionFilter
Tato třída interní rozšiřuje <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> třídy a představuje filtr pro testovací akce na [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] element.  
  
## <a name="simple-properties"></a>Jednoduché vlastnosti  
 Tyto vlastnosti jen pro čtení povolit vývojáře k určení, jak tento filtr akce testu se má provádět rozhraním framework programové testování uživatelského rozhraní. Například <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A> vlastnost poskytuje název filtru akce. Ostatní vlastnosti get <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A> filtru akce <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> název pro testovací akce, které jsou filtrovány podle tento filtr akce testu. Ostatní znamenat, jestli se má <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A> a také, jestli je akce testu <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A>.  
  
## <a name="processrule-method"></a>ProcessRule – metoda  
 Tato metoda je volána rozhraním framework programové testování uživatelského rozhraní a spouští filtr proti poskytnutého <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>. Odebere toto konkrétní přepsání myši vybrat akci na buňku, pokud další akce v zásobníku odešle stisknutí kláves do buňky. Pak vrátí `false`.  
  
## <a name="private-methods"></a>Privátní metody  
 `IsLeftClick` Metoda určuje, zda zadaná akce představuje klepnutí levým tlačítkem myši myši. `AreActionsOnSameExcelCell` Metoda určuje, zda dva zadané akce, které jsou provedeny na stejné buňky v aplikaci Excel.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>   
 [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
