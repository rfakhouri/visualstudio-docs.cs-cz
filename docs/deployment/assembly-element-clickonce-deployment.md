---
title: '&lt;sestavení&gt; – Element (nasazení ClickOnce) | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assembly> element [ClickOnce deployment manifest]
ms.assetid: b8e3362a-f821-4696-b98d-571d4bbfe431
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3b639a7f95cfb59844fa37963730e22ead450482
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56635459"
---
# <a name="ltassemblygt-element-clickonce-deployment"></a>&lt;sestavení&gt; – element (nasazení ClickOnce)
Element nejvyšší úrovně pro manifest nasazení.

## <a name="syntax"></a>Syntaxe

```xml

      <assembly  
   manifestVersion
/>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `assembly` Prvek je kořenovým elementem a je povinný. Musí být jeho první prvek `assemblyIdentity` elementu. Manifestu elementy musí být v následujících oborů názvů: `urn:schemas-microsoft-com:asm.v1`, `urn:schemas-microsoft-com:asm.v2`, a `http://www.w3.org/2000/09/xmldsig#`. Podřízené prvky prvku sestavení musí být také v těchto oborech názvů, dědičnosti nebo označování.

 `assembly` Element má tento atribut.

|Atribut|Popis|
|---------------|-----------------|
|`manifestVersion`|Povinný parametr. Tento atribut musí být nastaven `1.0`.|

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje `assembly` elementu v manifestu nasazení pro aplikace nasazené pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Tento příklad kódu je součástí většího příkladu určeného pro [Manifest nasazení ClickOnce](../deployment/clickonce-deployment-manifest.md) tématu.

```xml
<asmv1:assembly
  xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd"
  manifestVersion="1.0"
  xmlns:asmv3="urn:schemas-microsoft-com:asm.v3"
  xmlns:dsig=http://www.w3.org/2000/09/xmldsig#
  xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1"
  xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2"
  xmlns="urn:schemas-microsoft-com:asm.v2"
  xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"
  xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"
  xmlns:xrml="urn:mpeg:mpeg21:2003:01-REL-R-NS"
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
```

## <a name="see-also"></a>Viz také:
- [ClickOnce – manifest nasazení](../deployment/clickonce-deployment-manifest.md)
- [\<sestavení > – element](../deployment/assembly-element-clickonce-application.md)