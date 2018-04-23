---
title: '&lt;assemblyIdentity&gt; – Element (ClickOnce – nasazení) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assemblyIdentity
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assemblyIdentity> element [ClickOnce deployment manifest]
ms.assetid: f4a3bb83-c800-47d0-9905-9a5ae2486838
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 802d94063d2a4351ecc627c9426edb458d2543c2
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="ltassemblyidentitygt-element-clickonce-deployment"></a>&lt;assemblyIdentity&gt; – Element (ClickOnce – nasazení)
Určuje primární sestavení z [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      <assemblyIdentity    
   name   
   version  
   publicKeyToken  
   processorArchitecture  
    type  
/>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `assemblyIdentity` Prvek je nutný. Neobsahuje žádné podřízené elementy a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`name`|Požadováno. Určuje popisný název nasazení pro informační účely.<br /><br /> Pokud `name` obsahuje speciální znaky, jako je například jednoduché nebo dvojité uvozovky, může aplikace nepodaří aktivovat.|  
|`version`|Požadováno. Určuje číslo verze sestavení, v následujícím formátu: `major.minor.build.revision`.<br /><br /> Tato hodnota musí být zvýšena v aktualizovaném manifestu pro spuštění aktualizace aplikace.|  
|`publicKeyToken`|Požadováno. Určuje řetězec šestnáctkových 16 znaků, který představuje posledních 8 bajtů hodnoty hash SHA-1 veřejný klíč, pod kterým je podepsaný manifest nasazení. Veřejný klíč, který se používá k podepisování musí být 2048 bitů nebo vyšší.<br /><br /> I když podepsání sestavení je doporučená, ale volitelné, tento atribut je požadován. Pokud je sestavení bez znaménka, by měl zkopírujte hodnotu z podepsaného svým držitelem sestavení nebo použijte hodnotu "fiktivní" samými nulami.|  
|`processorArchitecture`|Požadováno. Určuje procesor. Platné hodnoty jsou `msil` pro všechny procesory `x86` pro 32bitový systém Windows, `IA64` pro 64bitový systém Windows, a `Itanium` pro procesory Intel 64-bit Itanium.|  
|`type`|Požadováno. K zajištění kompatibility se technologie Windows instalace vedle sebe. Pouze povolená hodnota je `win32`.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `assemblyIdentity` element v [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] – manifest nasazení. Tento příklad kódu je součástí většího příkladu vztahujícího se pro [Manifest aplikace ClickOnce](../deployment/clickonce-deployment-manifest.md) tématu.  
  
```  
<!-- Identify the deployment. -->  
<assemblyIdentity   
  name="My Application Deployment.app"  
  version="1.0.0.0"  
  publicKeyToken="43cb1e8e7a352766"  
  language="neutral"  
  processorArchitecture="x86"  
  xmlns="urn:schemas-microsoft-com:asm.v1" />  
```  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – Manifest nasazení](../deployment/clickonce-deployment-manifest.md)   
 [\<assemblyIdentity > elementu](../deployment/assemblyidentity-element-clickonce-application.md)