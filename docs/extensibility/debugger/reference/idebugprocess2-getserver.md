---
title: IDebugProcess2::GetServer | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProcess2::GetServer
helpviewer_keywords:
- IDebugProcess2::GetServer
ms.assetid: 8f73c530-cceb-4f1f-8c63-1cc0ccd4a310
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0d816393aa33c976b881a6e943fb1d27e44e9ff3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprocess2getserver"></a>IDebugProcess2::GetServer
Získá serveru, který tento proces běží na.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetServer(   
   IDebugCoreServer2** ppServer  
);  
```  
  
```csharp  
int GetServer(   
   out IDebugCoreServer2 ppServer  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppServer`  
 [out] Vrátí [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md) objekt, který představuje server, na kterém je spuštěn tento proces.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Více než jeden server může být spuštěn na jednom počítači.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)