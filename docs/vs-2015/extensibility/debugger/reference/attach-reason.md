---
title: ATTACH_REASON | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- ATTACH_REASON
helpviewer_keywords:
- ATTACH_REASON enumeration
ms.assetid: 159fb70b-a344-4ba6-9115-b7eaa16e228f
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c66894fe0515b28037bbb2a19715fa09cbf9fa62
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68153593"
---
# <a name="attachreason"></a>ATTACH_REASON
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Určuje důvod ladicího stroje (DE) k připojení k uzlu programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
typedef DWORD ATTACH_REASON;  
```  
  
```csharp  
public enum enum_ATTACH_REASON {   
   ATTACH_REASON_LAUNCH = 0x0001,  
   ATTACH_REASON_USER   = 0x0002,  
   ATTACH_REASON_AUTO   = 0x0003  
};  
```  
  
## <a name="members"></a>Členové  
 ATTACH_REASON_AUTO  
 Připojte, protože proces je aktuálně v režimu ladění.  
  
 ATTACH_REASON_LAUNCH  
 Připojte, protože proces byl spuštěn.  
  
 ATTACH_REASON_USER  
 Připojení z důvodu požadavku uživatele.  
  
## <a name="remarks"></a>Poznámky  
 Tyto hodnoty jsou použity jako parametr [připojit](../../../extensibility/debugger/reference/idebugengine2-attach.md) a [připojit](../../../extensibility/debugger/reference/idebugprogramex2-attach.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Výčty](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Připojení](../../../extensibility/debugger/reference/idebugengine2-attach.md)   
 [Attach](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)
