---
title: '&lt;dokument&gt; – element (vývoj pro Office v sadě Visual Studio)'
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.technology:
- office-development
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
manager: douge
ms.workload:
- office
ms.openlocfilehash: ac66f4f7dd458ecba5f26cc99ad795540dba648d
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/27/2018
ms.locfileid: "53802469"
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