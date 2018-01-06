---
title: "Ukázka rozšíření aplikace Excel: Třída ExtensionPackage | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e45410a-1819-4d54-ac21-7280152f7e3a
caps.latest.revision: "9"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: e216205ef2e7dfb22524ca3fb83a40958d31fd6d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
