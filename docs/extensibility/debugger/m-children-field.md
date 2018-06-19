---
title: m_children pole | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- m_children field, ContingentProperties class [.NET Framework debug engines]
ms.assetid: 0a3b5653-7bc0-4a7a-8963-9020bc52b9cb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e71bc592e77daac877b571b14acd2d62a8657b9f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109974"
---
# <a name="mchildren-field"></a>m_children pole
Seznam podřízené úlohy, které jsou registrované s touto úlohou.  
  
 **Namespace:** <xref:System.Threading.Tasks?displayProperty=fullName>  
  
 **Sestavení:** mscorlib (v mscorlib.dll)  
  
 Protože tento vnitřní člen nemůže získat přístup z rozhraní .NET Framework, je k dispozici společné Intermediate Language (soubor CIL) syntaxi.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.field public class System.Collections.Generic.List`1<class System.Threading.Tasks.Task> m_children  
```  
  
## <a name="remarks"></a>Poznámky  
 Když úloha běží, by měl k tomuto poli přístup pouze podproces, který provede úlohu.  
  
 Pokud je úloha dokončena, můžete jiná vlákna tak dlouho, dokud nic do ní přidejte nebo odeberte nic z něj přístup v tomto poli.  
  
## <a name="see-also"></a>Viz také  
 [ContingentProperties – třída](../../extensibility/debugger/contingentproperties-class-internal-members.md)