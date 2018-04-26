---
title: 'Ukázka rozšíření aplikace Excel: třída ActionFilter'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: sample
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: b15c0bbc76076178bdb541571e11a7599a3c46c2
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="sample-excel-extension-actionfilter-class"></a>Ukázka rozšíření aplikace Excel: třída ActionFilter

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
