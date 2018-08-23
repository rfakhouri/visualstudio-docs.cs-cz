---
title: CANSTOP_REASON | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CANSTOP_REASON
helpviewer_keywords:
- CANSTOP_REASON enumeration
ms.assetid: 6da944eb-36cd-4a8c-8d71-544c775cfcc1
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 6ea8242e4c7bdd820dd30cfb2c86cde60cda8bcd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671464"
---
# <a name="canstopreason"></a>CANSTOP_REASON
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [CANSTOP_REASON](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/canstop-reason).  
  
Umožňuje určit, pokud program můžete zastavit provádění po dosažení určitého bodu v provádění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_CANSTOP_REASON {   
   CANSTOP_ENTRYPOINT = 0x0000,  
   CANSTOP_STEPIN     = 0x0001  
};  
typedef DWORD CANSTOP_REASON;  
```  
  
```csharp  
public enum enum_CANSTOP_REASON {   
   CANSTOP_ENTRYPOINT = 0x0000,  
   CANSTOP_STEPIN     = 0x0001  
};  
```  
  
## <a name="members"></a>Členové  
 CANSTOP_ENTRYPOINT  
 Určuje vstupní bod určený program.  
  
 CANSTOP_STEPIN  
 Určuje vstup do funkce.  
  
## <a name="remarks"></a>Poznámky  
 Předán jako argument [getreason –](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md) metody pro potvrzení se relace ladění správce (SDM), pokud je v pořádku po dosažení vstupní bod programu nebo po přechodu na funkci nebo metodu.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Getreason –](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)

