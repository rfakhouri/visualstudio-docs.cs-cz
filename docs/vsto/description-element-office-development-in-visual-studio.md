---
title: '&lt;Popis&gt; – element (vývoj pro Office v sadě Visual Studio)'
titleSuffix: ''
ms.custom: secdec18
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- description element
- <description> element
- application manifests [Office development in Visual Studio], <description> element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ede5ac920c1d40402504544a13f8a00905b82e80
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62972379"
---
# <a name="ltdescriptiongt-element-office-development-in-visual-studio"></a>&lt;Popis&gt; – element (vývoj pro Office v sadě Visual Studio)
  `description` Elementu `vstov4` obor názvů obsahuje popis řešení pro Office, který se zobrazí v dialogovém okně Doplňky modelu COM z aplikace Microsoft Office.

## <a name="syntax"></a>Syntaxe

```xml
<description>
</description>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 Volitelné. `description` Elementu je `vstov4` oboru názvů. Obsahuje popis doplněk, který se zobrazí v dialogovém okně Doplňky modelu COM z aplikace Microsoft Office.

 `description` Prvek nemá žádné atributy nebo elementy.

## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO

### <a name="description"></a>Popis
 Následující příklad kódu ukazuje, `description` – element pro řešení úrovni aplikace nasazené s použitím [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kód

```xml
<vstov4:description>
  ContosoOutlookAddIn - Outlook add-in
  created with Visual Studio Tools for Office
</vstov4:description>
```

## <a name="see-also"></a>Viz také:

- [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md)