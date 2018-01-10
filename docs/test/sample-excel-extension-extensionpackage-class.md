---
title: "Ukázka rozšíření aplikace Excel: Třída ExtensionPackage | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 3603746325be5feff231d5e2538282f7bf6d6893
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="sample-excel-extension-extensionpackage-class"></a>Ukázka rozšíření aplikace Excel: třída ExtensionPackage
Tato třída rozšiřuje <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage> třídy a představuje vstupní bod pro programového testu uživatelského rozhraní, která je testování [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)] listu.  
  
## <a name="assembly-attribute"></a>Atribut sestavení  
 Soubor začíná sestavení atribut, který identifikuje sestavení jako rozšíření testu uživatelského rozhraní.  
  
```  
[assembly: Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage(  
    "ExcelExtensionPackage",  
    typeof(  
     Microsoft.VisualStudio.Test.Sample.UI.ExtensionPackage))]  
```  
  
 Tento atribut deklaruje název základní třídy, název balíčku třídy a plně kvalifikovaný název třídy pro třídu balíček vlastní rozšíření.  
  
## <a name="simple-properties"></a>Jednoduché vlastnosti  
 Tato třída obsahuje vlastnosti, které obsahují hodnoty, které jsou používány rámci programové testování uživatelského rozhraní pro identifikaci a popisují rozšíření a sestavení. Komentáře kódu pro další informace najdete.  
  
## <a name="getservice-method"></a>Metody GetService – metoda  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage.GetService%2A> Metoda je jeden vstupní bod použít rozhraním framework programové testování uživatelského rozhraní pro získání přístupu k manager technologie, vlastnost zprostředkovatele a filtr akcí, jako identifikovaný základní třídu pro každý objekt.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>   
 [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)
