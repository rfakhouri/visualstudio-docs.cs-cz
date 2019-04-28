---
title: '&lt;Vlastnost assemblyIdentity&gt; – Element (aplikace ClickOnce) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assemblyIdentity
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assemblyIdentity> element [ClickOnce application manifest]
ms.assetid: f48e9531-efac-4d11-8166-f63a5ece1ac5
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5bde22809af69071f5484e25717a5aea7d78a603
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62428531"
---
# <a name="ltassemblyidentitygt-element-clickonce-application"></a>&lt;Vlastnost assemblyIdentity&gt; – Element (aplikace ClickOnce)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Identifikuje nasazené v aplikaci [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] nasazení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      <assemblyIdentity   
   name  
   version  
   publicKeyToken  
   processorArchitecture  
   language  
/>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `assemblyIdentity` Je vyžadován element. Neobsahuje žádné podřízené prvky a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Name`|Povinný parametr. Určuje název aplikace.<br /><br /> Pokud `Name` obsahuje speciální znaky, jako je například jednoduché nebo dvojité uvozovky, aplikací se pravděpodobně nezdaří k aktivaci.|  
|`Version`|Povinný parametr. Určuje číslo verze aplikace v následujícím formátu: `major.minor.build.revision`|  
|`publicKeyToken`|Volitelné. Určuje šestnáctkový řetězec 16 znacích představující posledních 8 bajtů `SHA-1` hash hodnoty veřejný klíč, pod kterým je podepsaná aplikace nebo sestavení. Veřejný klíč, který se používá k podepsání katalogu musí být 2 048 bitů nebo vyšší.<br /><br /> I když se podpis sestavení se doporučuje, ale volitelné, tento atribut je vyžadován. Pokud je sestavení bez znaménka, by měl zkopírujte hodnotu z podepsaného sestavení nebo použijte hodnotu "fiktivní" samými nulami.|  
|`processorArchitecture`|Povinný parametr. Určuje procesor. Platné hodnoty jsou `msil` pro všechny procesory `x86` pro Windows 32-bit `IA64` pro Windows 64-bit, a `Itanium` pro procesory Itanium Intel 64-bit.|  
|`language`|Povinný parametr. Určuje jazyk kódy dvě součásti (například `en-US`) sestavení. Tento element má `asmv2` oboru názvů. Pokud tento parametr zadán, výchozí hodnota je `neutral`.|  
  
## <a name="examples"></a>Příklady  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `assemblyIdentity` prvek [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] manifest aplikace. Tento příklad kódu je součástí většího příkladu určeného v [Manifest aplikace ClickOnce](../deployment/clickonce-application-manifest.md).  
  
### <a name="code"></a>Kód  
  
```  
<asmv1:assemblyIdentity   
  name="My Application Deployment.exe"   
  version="1.0.0.0"   
  publicKeyToken="43cb1e8e7a352766"   
  language="neutral"   
  processorArchitecture="x86"   
  type="win32" />  
```  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – Manifest aplikace](../deployment/clickonce-application-manifest.md)   
 [Element \<assemblyIdentity>](../deployment/assemblyidentity-element-clickonce-deployment.md)
