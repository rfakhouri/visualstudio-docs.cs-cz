---
title: '&lt;formRegions&gt; – element (vývoj pro Office v sadě Visual Studio)'
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
- formRegions element
- <formRegions> element
- application manifests [Office development in Visual Studio], <formRegions> element
author: John-Hart
ms.author: johnhart
manager: douge
ms.workload:
- office
ms.openlocfilehash: d72206ac6ddd6696c1f2fac0f9de6552408a5a46
ms.sourcegitcommit: f6dd17b0864419083d0a1bf54910023045526437
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/27/2018
ms.locfileid: "53804588"
---
# <a name="ltformregionsgt-element-office-development-in-visual-studio"></a>&lt;formRegions&gt; – element (vývoj pro Office v sadě Visual Studio)
  `formRegions` Elementu `vstov4` obor názvů obsahuje oblastí formulářů aplikace Microsoft Office Outlook, které jsou spojeny s doplňku VSTO.

## <a name="syntax"></a>Syntaxe

```xml
<formRegions>
  <formRegion>
  </formRegion>
</formRegions>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `formRegions` Elementu `vstov4` obor názvů obsahuje všechny `formRegion` prvky pro doplňku VSTO v Outlooku. Je vyžadován pouze pro aplikaci Outlook doplňků VSTO, které zahrnují oblasti formuláře.

 Může existovat pouze jeden `formRegions` element definovaný v manifestu aplikace.

 `formRegions` Prvek nemá žádné atributy.

 `formRegions` Element má následující element.

### <a name="formregion"></a>formRegion
 Vyžaduje se pro aplikaci Outlook doplňků VSTO, které zahrnují oblasti formuláře. `formRegion` Element je definován v [ &#60;formRegion&#62; element &#40;vývoj pro Office v sadě Visual Studio&#41;](../vsto/formregion-element-office-development-in-visual-studio.md).

## <a name="vsto-add-in-example"></a>Příklad doplňku VSTO

### <a name="description"></a>Popis
 Následující příklad kódu ukazuje `formRegions` elementu v manifestu aplikace pro řešení Office úrovni aplikace nasazené pomocí [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kód

```xml
<vstov4:formRegions>
  <vstov4:formRegion
      name="OutlookAddIn1.FormRegion1">
    <vstov4:messageClass name="IPM.Note" />
    <vstov4:messageClass name="IPM.Contact" />
    <vstov4:messageClass name="IPM.Appointment" />
  </vstov4:formRegion>
</vstov4:formRegions>
```

## <a name="see-also"></a>Viz také:

- [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md)