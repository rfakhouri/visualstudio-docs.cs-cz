---
title: Ukázka rozšíření programového testu UI pro Excel | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- coded UI tests, extensions for Excel
ms.assetid: 451e4d14-7fac-42f9-af56-2bdc8414c6c7
caps.latest.revision: 15
ms.author: gewarren
manager: douge
ms.openlocfilehash: b4da574b77d8dd2b1b14ccb0b04e449799338620
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675078"
---
# <a name="sample-coded-ui-test-extension-for-excel"></a>Ukázka rozšíření programového testu UI pro Excel
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [ukázka programového uživatelského rozhraní testu rozšíření pro aplikaci Excel](https://docs.microsoft.com/visualstudio/test/sample-coded-ui-test-extension-for-excel).  
  
Komponenta rozšíření ukázky spuštěna v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] procesu programový Test uživatelského rozhraní a pomocí nich do jisté míry hierarchická `ExtensionPackage` základní třídy. `TechnologyManager`, `ActionFilter`, A `PropertyProvider` třídy se na další úrovni, ovládací prvky na nejvyšší úrovni.  
  
 ![Architektura přípony testu aplikace Excel](../test/media/excel-extarch.png "Excel_ExtArch")  
Architektura přípony aplikace Excel  
  
## <a name="extension-points"></a>Rozšiřovací body  
 Tyto třídy představují Rozšiřovací body, které jsou implementovány v ukázce povolení programového uživatelského rozhraní pro testování [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)].  
  
### <a name="extensionpackage"></a>ExtensionPackage  
 Zděděno z <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage> třídy, toto je vstupní bod pro programové testování rozšíření uživatelského rozhraní. Tato abstraktní třída implementace poskytuje kódované UI testování framework interní přístup k vlastní Správce technologie test uživatelského rozhraní, zprostředkovatel vlastnosti testu uživatelského rozhraní a filtr akce testu uživatelského rozhraní pro testování nové uživatelské rozhraní. Další informace najdete v tématu [třída ExtensionPackage](../test/sample-excel-extension-extensionpackage-class.md).  
  
### <a name="technologymanager"></a>TechnologyManager  
 Zděděno z <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager> třídy, tato třída poskytuje technologii správce pro zkušební záznam a přehrávání. Další informace najdete v tématu [třída TechnologyManager](../test/sample-excel-extension-technologymanager-class.md).  
  
### <a name="actionfilter"></a>ActionFilter  
 Zděděno z <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> třídy, tato třída poskytuje základní třídu pro agregaci podobné výsledky akce testu do výsledku jednoho testu. Další informace najdete v tématu [třída ActionFilter](../test/sample-excel-extension-actionfilter-class.md).  
  
### <a name="technology-elements"></a>Prvky technologie  
 Základní třída dědí z <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement> třída poskytuje základ pro prvky technologie ve vašich testech uživatelského rozhraní, které mohou být zaznamenány a přehrát. Další informace najdete v tématu [třídy Element](../test/sample-excel-extension-element-classes.md).  
  
### <a name="propertyprovider"></a>PropertyProvider  
 Zděděno z <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> třídy, tato třída poskytuje základní třídu pro podporu vlastnosti prvky uživatelského rozhraní pro test záznam a přehrávání. Další informace najdete v tématu [třída PropertyProvider](../test/sample-excel-extension-propertyprovider-class.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>   
 [Třída ExtensionPackage](../test/sample-excel-extension-extensionpackage-class.md)   
 [Třída TechnologyManager](../test/sample-excel-extension-technologymanager-class.md)   
 [Třída ActionFilter](../test/sample-excel-extension-actionfilter-class.md)   
 [Třídy element](../test/sample-excel-extension-element-classes.md)   
 [Třída PropertyProvider](../test/sample-excel-extension-propertyprovider-class.md)



