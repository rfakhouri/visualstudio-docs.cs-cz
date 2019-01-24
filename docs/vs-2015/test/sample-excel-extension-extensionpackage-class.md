---
title: 'Ukázka rozšíření Excel: Třída ExtensionPackage | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
ms.assetid: 6e45410a-1819-4d54-ac21-7280152f7e3a
caps.latest.revision: 11
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 668913d231115e955cc50df10de045eab3d4ac92
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54792018"
---
# <a name="sample-excel-extension-extensionpackage-class"></a>Ukázka rozšíření Excel: ExtensionPackage – třída
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato třída rozšiřuje <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage> třídy a představuje vstupní bod pro programový test UI, který je testování [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] listu.  
  
## <a name="assembly-attribute"></a>Atribut sestavení  
 Soubor se začne s atributem sestavení, který identifikuje sestavení jako rozšíření testu uživatelského rozhraní.  
  
```  
[assembly: Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage(  
    "ExcelExtensionPackage",  
    typeof(  
     Microsoft.VisualStudio.Test.Sample.UI.ExtensionPackage))]  
```  
  
 Tento atribut deklaruje název základní třídy, název třídy balíček a plně kvalifikovaný název třídy pro třídu vlastního rozšíření balíčku.  
  
## <a name="simple-properties"></a>Jednoduché vlastnosti  
 Tato třída obsahuje vlastnosti, které poskytují hodnoty, které se používají v rámci programových rozhraní testování uživatelského rozhraní k identifikují a popisují rozšíření a sestavení. Podívejte se v komentářích ke kódu pro další informace.  
  
## <a name="getservice-method"></a>Metoda GetService  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage.GetService%2A> Metoda je jeden vstupní bod, který používá testovací rozhraní programového uživatelského rozhraní pro získání přístupu k Správce technologie, zprostředkovatel vlastností a filtr akce pomocí základní třídy pro každý objekt.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>   
 [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
