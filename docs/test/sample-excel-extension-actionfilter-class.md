---
title: 'Ukázka rozšíření aplikace Excel: Třída Actionfilter | Microsoft Docs'
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 6f98afa819fceb4f8b8b34d5aa268f11f7b16993
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="sample-excel-extension-actionfilter-class"></a>Ukázka rozšíření aplikace Excel: Třída Actionfilter

Tato třída interní rozšiřuje <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> třídy a představuje filtr pro testovací akce na [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] element.

## <a name="simple-properties"></a>Jednoduché vlastnosti

Tyto vlastnosti jen pro čtení zadejte, jak se má provést filtr akce testu rozhraním framework programové testování uživatelského rozhraní. Například <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Name%2A> vlastnost poskytuje název filtru akce. Ostatní vlastnosti get <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Category%2A> filtru akce <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.FilterType%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Group%2A> název pro testovací akce, které jsou filtrovány podle tento filtr akce testu. Ostatní znamenat, jestli se má <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.ApplyTimeout%2A> a také, jestli je akce testu <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter.Enabled%2A>.

## <a name="processrule-method"></a>ProcessRule – metoda

Tato metoda je volána rozhraním framework programové testování uživatelského rozhraní a spouští filtr proti poskytnutého <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>. Odebere toto konkrétní přepsání myši vybrat akci na buňku, pokud další akce v zásobníku odešle stisknutí kláves do buňky. Pak vrátí `false`.

## <a name="private-methods"></a>Privátní metody

`IsLeftClick` Metoda určuje, zda zadaná akce představuje klepnutí levým tlačítkem myši myši. `AreActionsOnSameExcelCell` Metoda určuje, zda dva zadané akce, které jsou provedeny na stejné buňky v aplikaci Excel.

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.IUITestActionStack>
- [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
