---
title: '&lt;assemblyIdentity&gt; – Element (aplikace ClickOnce) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
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
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 86a9aedcd3f21d4dbc1cc4f09106421542b188f8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ltassemblyidentitygt-element-clickonce-application"></a>&lt;assemblyIdentity&gt; – Element (ClickOnce aplikace)
Identifikuje nasazené v aplikaci [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení.  
  
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
 `assemblyIdentity` Prvek je nutný. Neobsahuje žádné podřízené elementy a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Name`|Požadováno. Určuje název aplikace.<br /><br /> Pokud `Name` obsahuje speciální znaky, jako je například jednoduché nebo dvojité uvozovky, může aplikace nepodaří aktivovat.|  
|`Version`|Požadováno. Určuje číslo verze aplikace v následujícím formátu: `major.minor.build.revision`|  
|`publicKeyToken`|Volitelné. Určuje řetězec šestnáctkových 16 znaků, který představuje posledních 8 bajtů `SHA-1` hash hodnotu veřejný klíč, pod kterým je podepsaná aplikace nebo sestavení. Veřejný klíč, který se používá k podepisování katalogu musí být 2048 bitů nebo vyšší.<br /><br /> I když podepsání sestavení je doporučená, ale volitelné, tento atribut je požadován. Pokud je sestavení bez znaménka, by měl zkopírujte hodnotu z podepsaného svým držitelem sestavení nebo použijte hodnotu "fiktivní" samými nulami.|  
|`processorArchitecture`|Požadováno. Určuje procesor. Platné hodnoty jsou `msil` pro všechny procesory `x86` pro 32bitový systém Windows, `IA64` pro 64bitový systém Windows, a `Itanium` pro procesory Intel 64-bit Itanium.|  
|`language`|Požadováno. Identifikuje dvě součásti kódu jazyka (například `en-US`) sestavení. Tento element má `asmv2` oboru názvů. Pokud tento parametr nezadáte, výchozí hodnota je `neutral`.|  
  
## <a name="examples"></a>Příklady  
  
### <a name="description"></a>Popis  
 Následující příklad kódu ukazuje `assemblyIdentity` element v [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace. Tento příklad kódu je součástí většího příkladu vztahujícího se v [Manifest aplikace ClickOnce](../deployment/clickonce-application-manifest.md).  
  
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
 [\<assemblyIdentity > elementu](../deployment/assemblyidentity-element-clickonce-deployment.md)