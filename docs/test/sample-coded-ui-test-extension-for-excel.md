---
title: "Ukázka rozšíření programového testu UI pro Excel | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- coded UI tests, extensions for Excel
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: a446fbf087441be9e02c54314d05845ce759e47b
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
---
# <a name="sample-coded-ui-test-extension-for-excel"></a>Ukázka rozšíření programového testu UI pro Excel
Komponenta rozšíření vzorku spuštěna v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proces programového testu uživatelského rozhraní a je poněkud hierarchické s `ExtensionPackage` třída na bázi. `TechnologyManager`, `ActionFilter`, A `PropertyProvider` třídy jsou v dalším úrovni, se ovládací prvky na nejvyšší úrovni.

 ![Architektura přípony testu v aplikaci Excel](../test/media/excel_extarch.png "Excel_ExtArch") Architektura přípony v aplikaci Excel

## <a name="extension-points"></a>Rozšíření body
 Tyto třídy představují body rozšíření, které jsou implementované ve vzorku, chcete-li povolit programové uživatelského rozhraní pro testování [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)].

### <a name="extensionpackage"></a>ExtensionPackage
 Zděděno z <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage> třída, to je vstupní bod pro programové testování rozšíření uživatelského rozhraní. Tato abstraktní třída implementace poskytuje rozhraní programového testování framework interní přístup k vaší vlastní manager technologie testu uživatelského rozhraní, zprostředkovatele vlastnost testu uživatelského rozhraní a filtr akce testu uživatelského rozhraní pro testování nové uživatelské rozhraní. Další informace najdete v tématu [třída ExtensionPackage](../test/sample-excel-extension-extensionpackage-class.md).

### <a name="technologymanager"></a>TechnologyManager
 Zděděno z <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager> třída, tato třída poskytuje manažera technologie pro testovací záznam a přehrávání. Další informace najdete v tématu [třída Technologymanager](../test/sample-excel-extension-technologymanager-class.md).

### <a name="actionfilter"></a>ActionFilter
 Zděděno z <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> třídy, tato třída poskytuje základní třídu pro agregaci podobné výsledky akce testu do výsledku jeden test. Další informace najdete v tématu [třída Actionfilter](../test/sample-excel-extension-actionfilter-class.md).

### <a name="technology-elements"></a>Prvky technologie
 Základní třída zděděno z <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement> třída poskytuje základ pro prvky technologie ve vašich testech uživatelského rozhraní, které můžete zaznamenat a přehrání. Další informace najdete v tématu [třídy Element](../test/sample-excel-extension-element-classes.md).

### <a name="propertyprovider"></a>PropertyProvider
 Zděděno z <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> třída, tato třída poskytuje základní třídu pro podporu vlastnosti prvky uživatelského rozhraní pro test záznam a přehrávání. Další informace najdete v tématu [třída PropertyProvider](../test/sample-excel-extension-propertyprovider-class.md).

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>
- [ExtensionPackage – třída](../test/sample-excel-extension-extensionpackage-class.md)
- [TechnologyManager – třída](../test/sample-excel-extension-technologymanager-class.md)
- [ActionFilter – třída](../test/sample-excel-extension-actionfilter-class.md)
- [Třídy element](../test/sample-excel-extension-element-classes.md)
- [Třída PropertyProvider](../test/sample-excel-extension-propertyprovider-class.md)
