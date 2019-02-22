---
title: '&lt;Popis&gt; – Element (nasazení ClickOnce) | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#description
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <description> element [ClickOnce deployment manifest]
ms.assetid: 18f6919e-a3ab-4942-a57d-167fabfac44e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6c359b188894c40f017e3d2a0e06d52de87e9c5f
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56618559"
---
# <a name="ltdescriptiongt-element-clickonce-deployment"></a>&lt;Popis&gt; – element (nasazení ClickOnce)
Určuje informace o aplikaci použít k vytvoření prostředí prezentace a **přidat nebo odebrat programy** v Ovládacích panelech.

## <a name="syntax"></a>Syntaxe

```xml

      <description 
   publisher 
   product
   suiteName
   supportUrl
/>
```

## <a name="elements-and-attributes"></a>Elementy a atributy
 `description` Element je povinný a je v `urn:schemas-microsoft-com:asm.v1` oboru názvů. Neobsahuje žádné podřízené prvky a má následující atributy.

|Atribut|Popis|
|---------------|-----------------|
|`publisher`|Povinný parametr. Určuje název společnosti použít pro umístění ikony v Windows **Start** nabídky a **přidat nebo odebrat programy** v Ovládacích panelech, když je nasazení nakonfigurováno pro instalaci.|
|`product`|Povinný parametr. Určuje úplný název produktu. Použít jako název ikona nainstalované v Windows **Start** nabídky.|
|`suiteName`|Volitelné. Identifikuje podsložku v rámci `publisher` složky v Windows **Start** nabídky.|
|`supportUrl`|Volitelné. Určuje adresu URL podpory, který je zobrazen v **přidat nebo odebrat programy** v Ovládacích panelech. Je také vytvořen zástupce na tuto adresu URL pro podporu aplikace v Windows **Start** nabídky, pokud je nasazení nakonfigurováno pro instalaci.|

## <a name="remarks"></a>Poznámky
 Ve všech konfiguracích nasazení je vyžadován popis prvek.

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje `description` prvek [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifestu nasazení. Tento příklad kódu je součástí většího příkladu určeného pro [Manifest nasazení ClickOnce](../deployment/clickonce-deployment-manifest.md) tématu.

```xml
<description
  asmv2:publisher="My Company Name"
  asmv2:product="My Application"
  xmlns="urn:schemas-microsoft-com:asm.v1" />
```

## <a name="see-also"></a>Viz také:
- [ClickOnce – manifest nasazení](../deployment/clickonce-deployment-manifest.md)