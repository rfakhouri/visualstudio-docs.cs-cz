---
title: '&lt;vstupní bod&gt; – element (vývoj pro Office v sadě Visual Studio)'
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <entryPoint> element
- <entryPoint> element
- entryPoint element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: bd3da83a25a05690e56d229f61ee709473171dd7
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54873441"
---
# <a name="ltentrypointgt-element-office-development-in-visual-studio"></a>&lt;vstupní bod&gt; – element (vývoj pro Office v sadě Visual Studio)
  Každý `entryPoint` elementu `vstav3` obor názvů identifikuje vlastního nastavení sestavení, které by měla být spuštěna, když to [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] je aplikace nainstalovaná.

## <a name="syntax"></a>Syntaxe

```xml
<entryPoint class>
    <assemblyIdentity />
</entryPoint>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `entryPoint` Element je povinný a je v `vstav3` oboru názvů.

 Každý `entryPoint` element může obsahovat jenom jeden vlastní nastavení sestavení. Může existovat více `entryPoint` prvky definované v manifestu aplikace.

 `entryPoint` Element má následující atributy.

|Atribut|Popis|
|---------------|-----------------|
|`class`|Povinný parametr. Určuje vlastní nastavení sestavení má být proveden. Syntaxe pro tento atribut je *NamespaceName.ClassName*.|

 `entryPoint` má následující element.

### <a name="assemblyidentity"></a>assemblyIdentity
 Povinný parametr. `assemblyIdentity` Element v `vstav3` obor názvů odkazuje na existující `assemblyIdentity` prvek [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] manifest aplikace.

 Role `assemblyIdentity` a jeho atributy jsou definovány v [ &#60;assemblyIdentity&#62; element &#40;aplikace ClickOnce&#41;](../deployment/assemblyidentity-element-clickonce-application.md).

## <a name="document-level-customization-example"></a>Příklad přizpůsobení na úrovni dokumentu

### <a name="description"></a>Popis
 Následující příklad kódu ukazuje `entryPoint` prvky v aplikaci manifestu pro řešení Office úrovni dokumentu nasazeným v rámci [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kód

```xml
<vstav3:entryPoint
  class="ContosoExcelWorkbook.ThisWorkbook">
  <assemblyIdentity
    name="ContosoExcelWorkbook"
    version="1.0.0.0"
    language="neutral"
    processorArchitecture="msil" />
</vstav3:entryPoint>
<vstav3:entryPoint
  class="ContosoExcelWorkbook.Sheet1">
  <assemblyIdentity
    name="ContosoExcelWorkbook"
    version="1.0.0.0"
    language="neutral"
    processorArchitecture="msil" />
</vstav3:entryPoint>
<vstav3:entryPoint
  class="ContosoExcelWorkbook.Sheet2">
  <assemblyIdentity
    name="ContosoExcelWorkbook"
    version="1.0.0.0"
    language="neutral"
    processorArchitecture="msil" />
</vstav3:entryPoint>
<vstav3:entryPoint
  class="ContosoExcelWorkbook.Sheet3">
  <assemblyIdentity
    name="ContosoExcelWorkbook"
    version="1.0.0.0"
    language="neutral"
    processorArchitecture="msil" />
</vstav3:entryPoint>
```

## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO

### <a name="description"></a>Popis
 Následující příklad kódu ukazuje `entryPoint` elementu v manifestu aplikace pro řešení Office úrovni aplikace nasazené pomocí [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kód

```xml
<vstav3:entryPoint
  class="ContosoOutlookAddIn.ThisAddIn">
  <assemblyIdentity
    name="ContosoOutlookAddIn"
    version="1.0.0.0"
    language="neutral"
    processorArchitecture="msil" />
</vstav3:entryPoint>
```

## <a name="see-also"></a>Viz také:

- [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md)