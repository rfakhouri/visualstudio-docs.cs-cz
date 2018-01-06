---
title: "Ukázka rozšíření aplikace Excel: Třída PropertyProvider | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 075d9b8d-8658-4fca-8711-08304dbac1c5
caps.latest.revision: "9"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: 7617b7aafac6c7345a94d0e792bc312c7e212e56
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>   
 <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard>   
 [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
