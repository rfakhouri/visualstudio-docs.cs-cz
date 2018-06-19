---
title: '&lt;sestavení&gt; – Element (aplikace ClickOnce) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1c72dd684092784c88b1ef6dd76d410ac9ff84d5
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704220"
---
# <a name="ltassemblygt-element-clickonce-application"></a>&lt;sestavení&gt; – Element (ClickOnce aplikace)
Element nejvyšší úrovně pro manifest aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      <assembly  
   manifestVersion  
/>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `assembly` Element je kořenový element a musí se. Musí být jeho první prvek `assemblyIdentity` elementu. Manifestu elementy musí být v jednom z následujících oborů názvů:  
  
 `urn:schemas-microsoft-com:asm.v1`  
  
 `urn:schemas-microsoft-com:asm.v2`  
  
 `http://www.w3.org/2000/09/xmldsig#`  
  
 Podřízené elementy sestavení musí být také v těchto oborů názvů dědičnosti nebo označení.  
  
 `assembly` Element má následující atribut.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`manifestVersion`|Požadováno. `manifestVersion` Musí být nastaven `1.0`.|  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `assembly` element v manifestu aplikace pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. Tento příklad kódu je součástí většího příkladu vztahujícího se v [Manifest aplikace ClickOnce](../deployment/clickonce-application-manifest.md).  
  
```  
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
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – Manifest aplikace](../deployment/clickonce-application-manifest.md)   
 [\<sestavení > elementu](../deployment/assembly-element-clickonce-deployment.md)
