---
title: IDebugProgram2::Attach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::Attach
helpviewer_keywords:
- IDebugProgram2::Attach
ms.assetid: de069fbf-a565-4905-b102-f5658c55aacd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: aff1e5f6c887b42b6f49e0c8cfa426cade814006
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogram2attach"></a>IDebugProgram2::Attach
Připojí se k programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Attach(   
   IDebugEventCallback2* pCallback  
);  
```  
  
```csharp  
int Attach(   
   IDebugEventCallback2 pCallback  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pCallback`  
 [v] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objekt, který chcete použít pro oznámení o události ladění.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. V následující tabulce jsou uvedeny některé možné chybové kódy.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|Zadaný program je již připojen k ladicího programu.|  
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|Během procesu připojení došlo k narušení zabezpečení.|  
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|Desktopovému programu nelze připojit k ladicího programu.|  
  
## <a name="remarks"></a>Poznámky  
 Modul ladění (DE) nikdy volá tuto metodu za účelem připojení k programu. Pokud je DE spustí v programu adresního prostoru, [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) metoda je volána. Pokud se spustí DE ve Správci ladicí relace (SDM) adresní prostor, [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md) metoda je volána.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)