---
title: "Ukázka rozšíření aplikace Excel: Třídy Element | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: bd97702aec611a3818d478513a07ce03895729f3
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
---
# <a name="sample-excel-extension-element-classes"></a>Ukázka rozšíření Excel: Třídy Element
Používá rozšíření třídy, které jsou odvozeny od <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement> a představují listu ovládací prvky a buňky v [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)].

 Element base pro tuto příponu není `ExcelElement`. `ExcelWorksheetElement` Třídy a `ExcelCellElement` třídy dědí daný element

## <a name="element-and-elementinformation-classes"></a>Element a ElementInformation třídy
 `Element` Je základní třída pro všechny prvky uživatelského rozhraní pro rozšíření aplikace Excel a dědí z <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement> třídy. `ElementInformation` je základní třídou pro element třídy informace v ukázce a nemá žádné členy.

#### <a name="simple-properties-and-methods"></a>Jednoduché vlastnosti a metody
 Tito členové návratové jednoduché hodnoty, jako je například hodnota `Name` vlastnost nebo hodnotu `ClassName` vlastnost a kód je zrušte a snadno čitelný. Některé hodnoty jsou vráceny pomocí `Utility` třída, která je popsána později. Ostatní vrátit `null` protože nejsou v této ukázkové rozšíření relevantní. Dva členové jsou než ostatní zajímavějšího: <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.QueryId%2A> vlastnost a <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.CacheProperties%2A> metoda.

#### <a name="queryid-property"></a>Vlastnost QueryId
 Tato vlastnost vrátí podmínku, která se provádí z dvojice název hodnota vlastnosti, které jedinečně identifikují ovládacího prvku během přehrávání. Pro každou třídu odvozenou řízení vývojář musí přepsat tuto vlastnost se vrátíte <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IQueryElement> objektu, že rozhraní můžete použít k vyhledání ovládacího prvku v uživatelském rozhraní.

#### <a name="cacheproperties-method"></a>CacheProperties – metoda
 Tato metoda je volána rozhraním testování framework během procesu nahrávání říct elementu, který chcete uložit snímek důležité vlastnosti. Díky tomu vlastnosti, které jsou dostupné i v případě, že skutečný kontrolní mechanismus uživatelského rozhraní je už na obrazovce.

## <a name="worksheetelement-and-worksheetinformation-classes"></a>WorksheetElement a WorksheetInformation třídy
 `WorksheetElement` Třída reprezentuje listu aplikace Excel v rámci testování a dědí z `Element` základní třídy. Jsou tři vlastnosti přepsat a zadat konkrétní informace o objektu sešit aplikace Excel: <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.ClassName%2A>, <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.ControlTypeName%2A>, a <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.Name%2A>.

 <xref:System.Runtime.InteropServices.ComVisibleAttribute> Platí také pro tuto třídu zpřístupněte modelu COM.

 `WorksheetInformation` Třída reprezentuje informace o listu aplikace Excel. Má jenom jednoho člena `SheetName` vlastnost, která je pro tuto ukázku dostatečné.

## <a name="cellelement-and-cellinformation-classes"></a>CellElement a CellInformation třídy
 `CellElement` Třídy představuje buňku aplikaci Excel a zdědí `Element` základní třídy. Pouze přepsaného člen <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement.QueryId%2A> vlastnost, která vrací <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IQueryElement> používající `RowIndex` a `ColumnIndex` vlastnosti k identifikaci buňky.

## <a name="utilities-and-excelutilities-classes"></a>Nástroje a ExcelUtilities třídy
 Interní `ExcelUtilities` třída poskytuje konstantní hodnoty, jako je například název technologie a metodu, která určuje, pokud představuje popisovač zadaný okna listu aplikace Excel.

 `Utilities` Třída obsahuje pomocné metody, které vracejí různé informace o uživatelském rozhraní. Některé metody pomocí přímého volání do externího systému knihovny DLL, jako například **USER32. Knihovny DLL** a **OLEACC. Knihovny DLL**, abyste získali popisovače oken z uživatelského rozhraní**.**

## <a name="see-also"></a>Viz také

- <xref:System.Runtime.InteropServices.ComVisibleAttribute>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IQueryElement>
- [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
