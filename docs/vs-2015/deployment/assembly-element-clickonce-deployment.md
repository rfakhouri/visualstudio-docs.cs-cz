---
title: '&lt;sestavení&gt; – Element (nasazení ClickOnce) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assembly
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assembly> element [ClickOnce deployment manifest]
ms.assetid: b8e3362a-f821-4696-b98d-571d4bbfe431
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3b77cfacf3dca2c2cc20d674f79929e9958a16d4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54766604"
---
# <a name="ltassemblygt-element-clickonce-deployment"></a>&lt;sestavení&gt; – Element (nasazení ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Element nejvyšší úrovně pro manifest nasazení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
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
 Následující příklad kódu ukazuje `assembly` elementu v manifestu nasazení pro aplikace nasazené pomocí [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]. Tento příklad kódu je součástí většího příkladu určeného pro [Manifest nasazení ClickOnce](../deployment/clickonce-deployment-manifest.md) tématu.  
  
```  
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
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – Manifest nasazení](../deployment/clickonce-deployment-manifest.md)   
 [\<sestavení > – Element](../deployment/assembly-element-clickonce-application.md)
