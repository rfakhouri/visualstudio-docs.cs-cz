---
title: '&lt;sestavení&gt; – Element (aplikace ClickOnce) | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assembly> element [ClickOnce application manifest]
ms.assetid: 51410569-10f9-4c0a-96b5-d39185edbefc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6b629243920021adc3833f43f268f05638029dc7
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640399"
---
# <a name="ltassemblygt-element-clickonce-application"></a>&lt;sestavení&gt; – Element (aplikace ClickOnce)
Element nejvyšší úrovně pro manifest aplikace.

## <a name="syntax"></a>Syntaxe

```xml

      <assembly
   manifestVersion
/>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `assembly` Prvek je kořenovým elementem a je povinný. Musí být jeho první prvek `assemblyIdentity` elementu. Manifestu elementy musí být v jednom z následujících oborů názvů:

 `urn:schemas-microsoft-com:asm.v1`

 `urn:schemas-microsoft-com:asm.v2`

 `http://www.w3.org/2000/09/xmldsig#`

 Podřízené prvky prvku sestavení musí být také v těchto oborech názvů, dědičnosti nebo označování.

 `assembly` Element má tento atribut.

|Atribut|Popis|
|---------------|-----------------|
|`manifestVersion`|Povinný parametr. `manifestVersion` Atribut musí být nastaven na `1.0`.|

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje `assembly` elementu v manifestu aplikace pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. Tento příklad kódu je součástí většího příkladu určeného v [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md).

```xml
<asmv1:assembly
  xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd"
  manifestVersion="1.0"
  xmlns:asmv3="urn:schemas-microsoft-com:asm.v3"
  xmlns:dsig=http://www.w3.org/2000/09/xmldsig#
  xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2"
  xmlns="urn:schemas-microsoft-com:asm.v2"
  xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"
  xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"
  xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance
  xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1">
```

## <a name="see-also"></a>Viz také:
- [ClickOnce – manifest aplikace](../deployment/clickonce-application-manifest.md)
- [\<sestavení > – element](../deployment/assembly-element-clickonce-deployment.md)
