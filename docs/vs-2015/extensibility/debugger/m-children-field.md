---
title: m_children – pole | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- m_children field, ContingentProperties class [.NET Framework debug engines]
ms.assetid: 0a3b5653-7bc0-4a7a-8963-9020bc52b9cb
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a681f3a58fddbb136383a1259aa5e4c0c3b96b69
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49289625"
---
# <a name="mchildren-field"></a>m_children – pole
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Seznam podřízených úloh, které jsou registrované s touto úlohou.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v knihovně mscorlib.dll)  
  
 Protože tento člen interní nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.field public class System.Collections.Generic.List`1<class System.Threading.Tasks.Task> m_children  
```  
  
## <a name="remarks"></a>Poznámky  
 Když úloha běží, by měl přístup pouze vlákno, které provádí úlohy Toto pole.  
  
 Pokud úkol je dokončen, ostatní vlákna mohou přistupovat k toto pole, pokud cokoli do ní přidat nebo odebrat cokoli z něj.  
  
## <a name="see-also"></a>Viz také  
 [ContingentProperties – třída](../../extensibility/debugger/contingentproperties-class-internal-members.md)

