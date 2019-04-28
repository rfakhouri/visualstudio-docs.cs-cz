---
title: '&lt;publisherIdentity&gt; – Element (nasazení ClickOnce) | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- publisherIdentity Element [ClickOnce deployment manifest], introduction
- required element for signed manifests [ClickOnce], publisherIdentity Element
- publisherIdentity Element [ClickOnce deployment manifest], syntax, elements, and attributes
ms.assetid: 34c579db-d2f2-4b66-b9c8-47207f33d950
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 995b002784c1e76ceed36e51edb1ae893448f448
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62927536"
---
# <a name="ltpublisheridentitygt-element-clickonce-deployment"></a>&lt;publisherIdentity&gt; – element (nasazení ClickOnce)
Obsahuje informace o vydavateli, který podepsal manifestu nasazení.

## <a name="syntax"></a>Syntaxe

```xml
<publisherIdentity
   name
   issuerKeyHash
/>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `publisherIdentity` Vyžádáním – element pro podepsané manifesty. V následující tabulce jsou uvedeny atributy, které `publisherIdentity` elementu podporuje.

|Atribut|Popis|
|---------------|-----------------|
|`name`|Povinný parametr. Popisuje identity stranu, která publikovala tuto aplikaci.|
|`issuerKeyHash`|Povinný parametr. Obsahuje hodnotu hash SHA-1 veřejného klíče certifikátu vystavitele.|

#### <a name="parameters"></a>Parametry

## <a name="property-valuereturn-value"></a>Vlastnost hodnota nebo návratová hodnota

## <a name="exceptions"></a>Výjimky

## <a name="remarks"></a>Poznámky

## <a name="requirements"></a>Požadavky

## <a name="subhead"></a>Podnadpis