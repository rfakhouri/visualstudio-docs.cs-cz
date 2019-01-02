---
title: '&lt;postactiondata –&gt; – element (vývoj pro Office v sadě Visual Studio)'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- <postActionData> element
- application manifests [Office development in Visual Studio], <postActionData> element
- postActionData element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f27cf59f157c0760ea0c204a8c079dd4616777da
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53947267"
---
# <a name="ltpostactiondatagt-element-office-development-in-visual-studio"></a>&lt;postactiondata –&gt; – element (vývoj pro Office v sadě Visual Studio)
  `postActionData` Elementu `vstav3` data přidružená k žádné akci po nasazení, na kterém běží po instalaci řešení pro systém Office Určuje obor názvů.

## <a name="syntax"></a>Syntaxe

```xml
<postActionData>
</postActionData>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `postActionData` Element je volitelné a probíhá `vstav3` oboru názvů. Existuje jedna `postActionData` element definovaný v manifestu aplikace pro každou akci po nasazení.

 `postActions` Prvek nemá žádné atributy.

 `postActions` nemá žádný podřízený element.

## <a name="post-deployment-action-example"></a>Příklad akci po nasazení

### <a name="description"></a>Popis
 Následující příklad kódu ukazuje, `postAction` elementu v manifestu aplikace pro řešení Office nasazené s použitím [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kód

```xml
<vstav3:postActionData>
  data in any format
</vstav3:postActionData>
```

## <a name="see-also"></a>Viz také:

- [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md)
