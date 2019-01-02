---
title: '&lt;postactions –&gt; – element (vývoj pro Office v sadě Visual Studio)'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <postActions> element
- postActions element
- <postActions> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 2b719ec4b796e052abc018734b4acc3acbc0b138
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53845055"
---
# <a name="ltpostactionsgt-element-office-development-in-visual-studio"></a>&lt;postactions –&gt; – element (vývoj pro Office v sadě Visual Studio)
  `postActions` Elementu `vstav3` obor názvů obsahuje všechny `postAction` prvky, které obsahují popis akcí po nasazení, které se spustí po dokončení instalace řešení pro systém Office.

## <a name="syntax"></a>Syntaxe

```xml
<postActions>
  <postAction>
    <entryPoint>
    </entryPoint>
    <postActionData>
    </postActionData>
  </postAction>
</postActions>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `postActions` Element je volitelný a je v `vstav3` oboru názvů. Existuje pouze jeden `postActions` element definovaný v manifestu aplikace.

 `postActions` Prvek nemá žádné atributy.

 `postActions` má následující element.

### <a name="postaction"></a>postAction
 Volitelné. Role `postAction` prvek `vstav3` obor názvů je definovaný v [ &#60;postAction&#62; element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/postaction-element-office-development-in-visual-studio.md).

## <a name="post-deployment-action-example"></a>Příklad akci po nasazení

### <a name="description"></a>Popis
 Následující příklad kódu ukazuje, `postActions` elementu v manifestu aplikace pro řešení Office nasazené s použitím [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kód

```xml
<vstav3:postActions>
  <vstav3:postAction>
    <vstav3:entryPoint
      class="PostDeploymentAction.PostDeploymentActionSample">
      <assemblyIdentity
        name="PostDeploymentAction"
        version="1.0.0.0"
        language="neutral"
        processorArchitecture="msil" />
    </vstav3:entryPoint>
    <vstav3:postActionData>
    </vstav3:postActionData>
  </vstav3:postAction>
</vstav3:postActions>
```

## <a name="see-also"></a>Viz také:

- [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md)
