---
title: '&lt;formRegion&gt; – element (vývoj pro Office v sadě Visual Studio)'
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio], <formRegion> element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 33bc2ce58f90f37a1219427558a01bd13e5654df
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62414536"
---
# <a name="ltformregiongt-element-office-development-in-visual-studio"></a>&lt;formRegion&gt; – element (vývoj pro Office v sadě Visual Studio)
  `formRegion` Elementu `vstov4` obor názvů identifikuje oblasti formuláře aplikace Microsoft Office Outlook, který je přidružený k doplňku VSTO.

## <a name="syntax"></a>Syntaxe

```xml
<formRegion
  name>
  <messageClass
    name/>
</formRegion>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `formRegion` Elementu `vstov4` obor názvů identifikuje oblasti formuláře, který je přidružený doplňku VSTO v Outlooku. Je vyžadován pouze pro aplikaci Outlook doplňků VSTO, které zahrnují oblasti formuláře.

 Může existovat více `formRegion` elementy definované uvnitř `formRegions` – element pro jednoho doplňku VSTO.

 `formRegion` Element má tento atribut.

|Atribut|Popis|
|---------------|-----------------|
|`name`|Povinný parametr. Určuje název oblasti formuláře.|

 `formRegion` Element má následující podřízené prvky.

### <a name="messageclass"></a>Třída messageClass
 `messageClass` Element identifikuje formuláře aplikace Outlook, který je přidružený k oblasti formuláře.

 `messageClass` Element má tento atribut.

|Atribut|Popis|
|---------------|-----------------|
|`name`|Povinný parametr. Identifikuje formulář, který je přidružený k oblasti formuláře.|

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje `formRegion` elementu v manifestu aplikace pro Outlook VSTO doplněk nasazeným v rámci [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Existují tři třídy zpráv, které jsou přidružené k této oblasti jeden formulář. Tento příklad kódu je součástí většího příkladu určeného v [manifesty aplikace pro řešení Office](../vsto/application-manifests-for-office-solutions.md).

```xml
<vstov4:formRegion
    name="OutlookAddIn1.FormRegion1">
  <vstov4:messageClass name="IPM.Note" />
  <vstov4:messageClass name="IPM.Contact" />
  <vstov4:messageClass name="IPM.Appointment" />
</vstov4:formRegion>
```

## <a name="see-also"></a>Viz také:

- [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)
- [Manifesty aplikace pro řešení pro systém Office](../vsto/application-manifests-for-office-solutions.md)
- [Manifesty nasazení pro řešení pro systém Office](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md)