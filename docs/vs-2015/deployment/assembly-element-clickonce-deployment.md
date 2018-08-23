---
title: '&lt;sestavení&gt; – Element (nasazení ClickOnce) | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
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
manager: wpickett
ms.openlocfilehash: 96978ec8329ddf31b2cc641bf02d2b38a9e98f4a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668744"
---
# <a name="ltassemblygt-element-clickonce-deployment"></a>&lt;sestavení&gt; – Element (nasazení ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [ &lt;sestavení&gt; – Element (nasazení ClickOnce)](https://docs.microsoft.com/visualstudio/deployment/assembly-element-clickonce-deployment).  
  
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
|`manifestVersion`|Požadováno. Tento atribut musí být nastaven `1.0`.|  
  
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



