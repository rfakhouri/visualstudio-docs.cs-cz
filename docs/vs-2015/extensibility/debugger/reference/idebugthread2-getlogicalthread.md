---
title: IDebugThread2::GetLogicalThread | Dokumentace Microsoftu
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
- IDebugThread2::GetLogicalThread
helpviewer_keywords:
- IDebugThread2::GetLogicalThread
ms.assetid: bce6230e-41d4-49b7-a050-2dde5efb6805
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 012cb13e2319e421f6efa3e7ec897a30c83c1e1e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633594"
---
# <a name="idebugthread2getlogicalthread"></a>IDebugThread2::GetLogicalThread
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugThread2::GetLogicalThread](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugthread2-getlogicalthread).  
  
Ladicí stroj neimplementují této metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT GetLogicalThread(   
   IDebugStackFrame2*     pStackFrame,  
   IDebugLogicalThread2** ppLogicalThread  
);  
```  
  
```csharp  
int GetLogicalThread(   
   IDebugStackFrame2        pStackFrame,  
   out IDebugLogicalThread2 ppLogicalThread  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pStackFrame`  
 [in] [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) objekt představující rámec zásobníku.  
  
 `ppLogicalThread`  
 [out] Vrátí `IDebugLogicalThread2` rozhraní, které představuje přidružené logické vlákno. Implementace modulu ladění by měl nastavíte na hodnotu null.  
  
## <a name="return-value"></a>Návratová hodnota  
 Ladění vždy návratový stroj implementace `E_NOTIMPL`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)

