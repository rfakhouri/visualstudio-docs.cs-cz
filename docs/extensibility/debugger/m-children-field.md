---
title: m_children – pole | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- m_children field, ContingentProperties class [.NET Framework debug engines]
ms.assetid: 0a3b5653-7bc0-4a7a-8963-9020bc52b9cb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0f8ea4f053d28ea14c05a50e3bc187faf6f6e207
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54966852"
---
# <a name="mchildren-field"></a>m_children – pole
Seznam podřízených úloh, které jsou registrované s touto úlohou.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v *mscorlib.dll*)  
  
 Protože tento člen interní nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```csharp 
.field public class System.Collections.Generic.List`1<class System.Threading.Tasks.Task> m_children  
```  
  
## <a name="remarks"></a>Poznámky  
 Když úloha běží, by měl přístup pouze vlákno, které provádí úlohy Toto pole.  
  
 Pokud je úkol dokončen, ostatní vlákna tak dlouho, dokud není nic k němu přidat nebo odebrat cokoli z něj přístupná toto pole.  
  
## <a name="see-also"></a>Viz také:  
 [Třída ContingentProperties](../../extensibility/debugger/contingentproperties-class-internal-members.md)