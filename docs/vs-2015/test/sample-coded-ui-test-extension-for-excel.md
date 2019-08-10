---
title: Ukázka rozšíření programového testu UI pro Excel | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- coded UI tests, extensions for Excel
ms.assetid: 451e4d14-7fac-42f9-af56-2bdc8414c6c7
caps.latest.revision: 15
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f550e65a152e06ab49ab8a0b3f213edffcf89cd3
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68871624"
---
# <a name="sample-coded-ui-test-extension-for-excel"></a>Ukázka rozšíření programového testu UI pro Excel
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Součást rozšíření v ukázce se spouští v [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] procesu programového testu uživatelského rozhraní a je trochu hierarchicky `ExtensionPackage` se třídou v základní třídě. Třídy `TechnologyManager`, `ActionFilter` a`PropertyProvider` jsou na další úrovni s ovládacími prvky na nejvyšší úrovni.

 ![Architektura testovacího rozšíření aplikace Excel](../test/media/excel-extarch.png "Excel_ExtArch") Architektura rozšíření aplikace Excel

## <a name="extension-points"></a>Rozšiřovací body
 Tyto třídy představují Rozšiřovací body, které jsou implementovány v ukázce pro povolení programového testování uživatelského [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)]rozhraní pro.

### <a name="extensionpackage"></a>ExtensionPackage
 Zděděno od <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage> třídy, toto je vstupní bod pro rozšíření programového testování uživatelského rozhraní. Implementace této abstraktní třídy poskytuje programový test UI Framework interní přístup k vašemu vlastnímu Správci technologie testování uživatelského rozhraní, poskytovateli vlastností testu uživatelského rozhraní a filtru akcí testu uživatelského rozhraní pro testování nového uživatelského rozhraní. Další informace naleznete v tématu [Třída ExtensionPackage](../test/sample-excel-extension-extensionpackage-class.md).

### <a name="technologymanager"></a>TechnologyManager
 Tato třída zděděná od <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager> třídy poskytuje vedoucímu pro nahrávání a přehrávání testů. Další informace naleznete v tématu [Třída TechnologyManager](../test/sample-excel-extension-technologymanager-class.md).

### <a name="actionfilter"></a>ActionFilter
 Tato třída je zděděná od třídy [UITestActionFilter](/previous-versions/visualstudio/visual-studio-2012/dd985757(v=vs.110)) a poskytuje základní třídu pro agregaci podobných výsledků testovacích akcí do jednoho výsledku testu. Další informace naleznete v tématu [třída ActionFilter](../test/sample-excel-extension-actionfilter-class.md).

### <a name="technology-elements"></a>Prvky technologie
 Základní třída zděděná z <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement> třídy poskytuje základ pro prvky technologie ve vašich testech uživatelského rozhraní, které je možné zaznamenat a přehrát zpátky. Další informace naleznete v tématu [třídy prvků](../test/sample-excel-extension-element-classes.md).

### <a name="propertyprovider"></a>PropertyProvider
 Tato třída je <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> zděděná od třídy a poskytuje základní třídu pro podporu vlastností prvků uživatelského rozhraní pro nahrávání a přehrávání testů. Další informace naleznete v tématu [Třída PropertyProvider](../test/sample-excel-extension-propertyprovider-class.md).

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>
- <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>
- [ExtensionPackage – třída](../test/sample-excel-extension-extensionpackage-class.md)
- [TechnologyManager – třída](../test/sample-excel-extension-technologymanager-class.md)
- [ActionFilter – třída](../test/sample-excel-extension-actionfilter-class.md)
- [Třídy Element](../test/sample-excel-extension-element-classes.md)
- [PropertyProvider – třída](../test/sample-excel-extension-propertyprovider-class.md)
