---
title: '&lt;dokument&gt; – element (vývoj pro Office v sadě Visual Studio)'
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document element
- application manifests [Office development in Visual Studio], <document> element
- <document> element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 36d822d60d1a28d48f660f6d358b75bf4a913048
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63000022"
---
# <a name="ltdocumentgt-element-office-development-in-visual-studio"></a>&lt;dokument&gt; – element (vývoj pro Office v sadě Visual Studio)
  `document` Elementu `vstov4` obor názvů obsahuje informace specifické pro přizpůsobení pro přizpůsobení na úrovni dokumentu.

## <a name="syntax"></a>Syntaxe

```xml
<document solutionId />
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 Vyžaduje se jenom pro přizpůsobení na úrovni dokumentu. `document` Elementu je `vstov4` oboru názvů. `document` Element má následující atributy.

|Atribut|Popis|
|---------------|-----------------|
|`solutionId`|Povinný parametr. Identifikátor GUID, který používá Visual Studio Tools for Office runtime k jednoznačné identifikaci řešení úrovni dokumentu. Tato hodnota bude uložena jako _AssemblyLocation vlastní vlastnost dokumentu. Další informace najdete v tématu [přehled vlastností dokumentu vlastní](../vsto/custom-document-properties-overview.md).|

 `document` nemá žádný podřízený element.

## <a name="document-level-customization-example"></a>Příklad přizpůsobení na úrovni dokumentu

### <a name="description"></a>Popis
 Následující příklad kódu ukazuje, `document` prvek v řešení pro Office úrovni dokumentu nasazené s použitím [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kód

```xml
<vstov4:document
  solutionId="73e" />
```

## <a name="see-also"></a>Viz také:

- [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md)