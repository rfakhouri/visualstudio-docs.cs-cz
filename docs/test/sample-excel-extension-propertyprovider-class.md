---
title: 'Ukázka rozšíření aplikace Excel: třída PropertyProvider'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: sample
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: e4a1e96fc666275d83cf0f32edf00f0fc2f6c03c
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="sample-excel-extension-propertyprovider-class"></a>Ukázka rozšíření aplikace Excel: třída PropertyProvider
Tato interní třída rozšiřuje <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> třídy a poskytuje služby vlastnost pro [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] elementy pro záznam a přehrávání testů uživatelského rozhraní (UI).

## <a name="getcontrolsupportlevel-method"></a>GetControlSupportLevel – metoda
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetControlSupportLevel%2A> Metoda vrátí číslo, které informuje o úrovni podpory, který vám může nabídnout poskytovatel vlastnost pro zadaný ovládací prvek. Čím vrácené hodnoty, další vlastnosti zprostředkovatele může podporovat ovládacího prvku. V takovém případě zkontroluje tato metoda hodnotu <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IUITechnologyElement.TechnologyName%2A> vlastnost zadaný ovládacího prvku. Pokud je hodnota "Excel" a pokud <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IUITechnologyElement.ControlTypeName%2A> označuje je `CellElement`, metoda vrátí nejvyšší hodnotu; jinak vrátí nulové hodnoty, který označuje, že žádná podpora je k dispozici.

## <a name="getpropertynames-method"></a>GetPropertyNames – metoda
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
