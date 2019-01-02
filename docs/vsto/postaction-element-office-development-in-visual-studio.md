---
title: '&lt;postAction&gt; – element (vývoj pro Office v sadě Visual Studio)'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <postAction> element
- <postAction> element
- postAction element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1886a1c0be486cfae8e85d0accd0fb42dc5d5353
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53958797"
---
# <a name="ltpostactiongt-element-office-development-in-visual-studio"></a>&lt;postAction&gt; – element (vývoj pro Office v sadě Visual Studio)
  `postAction` Elementu `vstav3` obsahuje obor názvů `entrypoint` elementy a všechny `postActionData` prvky, které souvisejí s akcemi po nasazení, které se spustí po dokončení instalace řešení pro systém Office.

## <a name="syntax"></a>Syntaxe

```xml
<postAction>
  <entryPoint>
  </entryPoint>
  <postActionData>
  </postActionData>
</postAction>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `postAction` Element je volitelný a je v `vstav3` oboru názvů. Existuje jedna `postAction` element definovaný v manifestu aplikace pro každou akci po nasazení.

 `postAction` Prvek nemá žádné atributy.

 `postAction` obsahuje následující prvky.

### <a name="entrypoint"></a>Vstupní bod
 Volitelné. Role `entryPoint` prvek `vstav3` obor názvů je definovaný v [ &#60;entryPoints&#62; element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/entrypoints-element-office-development-in-visual-studio.md).

### <a name="postactiondata"></a>postactiondata –
 Volitelné. Role `postActionData` prvek `vstav3` obor názvů je definovaný v [ &#60;postactiondata –&#62; element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/postactiondata-element-office-development-in-visual-studio.md).

## <a name="post-deployment-action-example"></a>Příklad akci po nasazení

### <a name="description"></a>Popis
 Následující příklad kódu ukazuje, `postAction` elementu v manifestu aplikace pro řešení Office, který se nasazuje s použitím [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kód

```xml
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
```

## <a name="see-also"></a>Viz také:

- [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md)
