---
title: '&lt;vstoruntime –&gt; – element (vývoj pro Office v sadě Visual Studio)'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <vstoRuntime> element
- <vstoRuntime> element
- vstoRuntime element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 80ef1c8e347aa2447ff48838015bb6499236e123
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/27/2018
ms.locfileid: "53802660"
---
# <a name="ltvstoruntimegt-element-office-development-in-visual-studio"></a>&lt;vstoruntime –&gt; – element (vývoj pro Office v sadě Visual Studio)
  `vstoRuntime` Elementu `vstav3` obor názvů obsahuje podporovanou verzi sady Visual Studio Tools for Office runtime pro konkrétní řešení Office.

## <a name="syntax"></a>Syntaxe

```xml
<vstoRuntime
    release
    version
    supportUrl />
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `vstoRuntime` Element je povinný a je v `vstav3` oboru názvů. Pokud řešení pro Office podporuje dvě verze nástroje Visual Studio Tools pro systém Office runtime, existují dva `vstoRuntime` prvky v manifestu aplikace.

 `vstoRuntime` Element má následující atributy.

|Atribut|Popis|
|---------------|-----------------|
|`release`|Povinný parametr. Verze sady Visual Studio Tools for Office runtime.|
|`version`|Povinný parametr. Číslo verze sady Visual Studio Tools for Office runtime.|
|`supportUrl`|Volitelné. Odkaz na umístění instalace sady Visual Studio Tools for Office runtime.|

 `vstoRuntime` neobsahuje žádné prvky.

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje, `vstoRuntime` elementu v manifestu aplikace pro řešení Office nasazené s použitím [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

```xml
<vstav3:vstoRuntime
    release="VSTOR40Beta1"
    version="10.0.20303"
    supportUrl="http://www.microsoft.com" />
```

## <a name="see-also"></a>Viz také:

- [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md)
