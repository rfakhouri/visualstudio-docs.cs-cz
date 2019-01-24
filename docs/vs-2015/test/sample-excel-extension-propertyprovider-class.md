---
title: 'Ukázka rozšíření Excel: Třída PropertyProvider | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
ms.assetid: 075d9b8d-8658-4fca-8711-08304dbac1c5
caps.latest.revision: 11
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d38b430dd88eb1a732c4e4ca335a0a5bb057b1f4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54801247"
---
# <a name="sample-excel-extension-propertyprovider-class"></a>Ukázka rozšíření Excel: PropertyProvider – třída
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tento vnitřní třída rozšiřuje <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> třídy a nabízí vlastnosti pro [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] prvků, které se záznam a přehrávání testů uživatelského rozhraní (UI).  
  
## <a name="getcontrolsupportlevel-method"></a>GetControlSupportLevel – metoda  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider.GetControlSupportLevel%2A> Metoda vrátí číslo určující úroveň podpory, které může nabídnout poskytovatel vlastností pro zadaný ovládací prvek. Další vlastnosti zprostředkovatele je vrácená hodnota vyšší, může podporovat ovládacího prvku. V takovém případě metoda zkontroluje hodnotu vlastnosti <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IUITechnologyElement.TechnologyName%2A> vlastnost zadaný ovládacího prvku. Pokud je hodnota "Excel" a pokud <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.IUITechnologyElement.ControlTypeName%2A> značí, že je `CellElement`, metoda vrátí nejvyšší hodnotu; jinak vrací 0, což znamená, že nenabízí žádnou podporu.  
  
## <a name="getpropertynames-method"></a>GetPropertyNames – metoda  
 Vrátí slovník názvů vlastností a popisovače vlastnosti pro podporovaných vlastností ovládacího prvku Excelové buňky.  
  
## <a name="getpropertydescriptor-method"></a>GetPropertyDescriptor – metoda  
 Tato metoda je volána v rámci testovacího rozhraní se získat popisovač předdefinované vlastnosti pro poskytnutý název vlastnosti.  
  
## <a name="getpropertyvalue-and-setpropertyvalue-methods"></a>GetPropertyValue a SetPropertyValue metody  
 `GetPropertyValue` Metoda používá `Communicator` třídy tohoto rozšíření k vrácení hodnoty vlastnosti z aplikace Excel. `SetPropertyValue` Metoda používá <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard> třídy a `Communicator` součást pro nastavení hodnoty vlastnosti. Tyto metody jsou volány testovací rozhraní.  
  
## <a name="code-generation-customization-methods"></a>Metody přizpůsobení generování kódu  
 Tyto metody nejsou implementovány pro tuto příponu. Proto, že buď vrátit `null` nebo vyvolat <xref:System.NotImplementedException>.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>   
 <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard>   
 [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
