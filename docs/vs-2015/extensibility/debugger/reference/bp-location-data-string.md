---
title: BP_LOCATION_DATA_STRING | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- BP_LOCATION_DATA_STRING
helpviewer_keywords:
- BP_LOCATION_DATA_STRING structure
ms.assetid: 445d6f3f-95b0-47ac-85e2-51b778240687
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 92fbda278b0e0c4f4ee5a39cc13f80b5fbd2bbb7
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49889084"
---
# <a name="bplocationdatastring"></a>BP_LOCATION_DATA_STRING
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Používá k nastavení datové zarážky, které jsou založeny na řetězec, který může uživatel zadat z integrovaného vývojového prostředí (IDE).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
typedef struct _BP_LOCATION_DATA_STRING {   
   IDebugThread2* pThread;  
   BSTR           bstrContext;  
   BSTR           bstrDataExpr;  
   DWORD          dwNumElements;  
} BP_LOCATION_DATA_STRING;  
```  
  
## <a name="members"></a>Členové  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) objekt, který reprezentuje vlákno, na kterém dochází k zarážce.  
  
 `bstrContext`  
 Kontext zarážky v kódu, obvykle název metody nebo funkce jako zobrazení zásobníku volání.  
  
 `bstrDataExpr`  
 Řetězec dat, které uživatel zadá nastavit zarážku.  
  
 `dwNumElements`  
 Počet prvků v řetězci data, ve kterém dochází k zarážce.  
  
## <a name="remarks"></a>Poznámky  
 Tato struktura je členem skupiny [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) struktury v rámci sjednocení.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Struktury a sjednocení](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)

