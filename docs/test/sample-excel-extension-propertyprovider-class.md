---
title: "Ukázka rozšíření aplikace Excel: Třída PropertyProvider | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: c8917661d4df4034cfb97a94c7a515659c558da5
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="sample-excel-extension-propertyprovider-class"></a>Ukázka rozšíření aplikace Excel: třída PropertyProvider
Tato interní třída rozšiřuje <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> třídy a poskytuje služby vlastnost pro [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] elementy pro záznam a přehrávání testů uživatelského rozhraní (UI).

## <a name="getcontrolsupportlevel-method"></a>GetControlSupportLevel – metoda
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetControlSupportLevel%2A> Metoda vrátí číslo, které informuje o úrovni podpory, který vám může nabídnout poskytovatel vlastnost pro zadaný ovládací prvek. Čím vrácené hodnoty, další vlastnosti zprostředkovatele může podporovat ovládacího prvku. V takovém případě zkontroluje tato metoda hodnotu <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IUITechnologyElement.TechnologyName%2A> vlastnost zadaný ovládacího prvku. Pokud je hodnota "Excel" a pokud <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IUITechnologyElement.ControlTypeName%2A> označuje je `CellElement`, metoda vrátí nejvyšší hodnotu; jinak vrátí nulové hodnoty, který označuje, že žádná podpora je k dispozici.

## <a name="getpropertynames-method"></a>GetPropertyNames Method
 Vrátí slovník názvů vlastností a popisovače vlastnosti pro podporovaných vlastností ovládacího prvku buňky aplikace Excel.

## <a name="getpropertydescriptor-method"></a>GetPropertyDescriptor – metoda
 Tato metoda je volána rozhraním testování framework se získat popisovač předdefinované vlastnosti pro název zadané vlastnosti.

## <a name="getpropertyvalue-and-setpropertyvalue-methods"></a>GetPropertyValue a SetPropertyValue metody
 `GetPropertyValue` Metoda používá `Communicator` třída tohoto rozšíření vrácení hodnoty vlastnosti z aplikace Excel. `SetPropertyValue` Metoda používá <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard> třídy a `Communicator` součást, kterou nastavit hodnotu vlastnosti. Tyto metody jsou volány testování framework.

## <a name="code-generation-customization-methods"></a>Metod přizpůsobení generování kódu
 Tyto metody nejsou implementované pro tuto příponu. Proto, že budou buď vracet `null` nebo throw <xref:System.NotImplementedException>.

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>
- <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard>
- [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
