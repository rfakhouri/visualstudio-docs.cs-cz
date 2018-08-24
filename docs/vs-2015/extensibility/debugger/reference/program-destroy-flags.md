---
title: PROGRAM_DESTROY_FLAGS | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PROGRAM_DESTROY_FLAGS enumeration
ms.assetid: be00d4a3-d5b8-4159-b632-64577f534883
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c82229526123386f752d723dc432b6e91bba71ce
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670478"
---
# <a name="programdestroyflags"></a>PROGRAM_DESTROY_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [PROGRAM_DESTROY_FLAGS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/program-destroy-flags).  
  
Vytvoří výčet platnými hodnoty programu zničit příznaky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_PPROGRAM_DESTROY_FLAGS  
{  
   PROGRAM_DESTROY_CONTINUE_DEBUGGING = 0x1  
};  
typedef DWORD PROGRAM_DESTROY_FLAGS;  
```  
  
```csharp  
public enum enum_PPROGRAM_DESTROY_FLAGS  
{  
   PROGRAM_DESTROY_CONTINUE_DEBUGGING = 0x1  
};  
```  
  
## <a name="terms"></a>Podmínky  
 PROGRAM_DESTROY_CONTINUE_DEBUGGING  
 Odstranit program, ale pokračujte v ladění.  
  
## <a name="remarks"></a>Poznámky  
 Výčet je vrácený [getflags –](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Getflags –](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md)

