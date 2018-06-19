---
title: IDebugDefaultPort2::GetServer | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDefaultPort2::GetServer
helpviewer_keywords:
- IDebugDefaultPort2::GetServer
ms.assetid: cacb4b74-0f39-471c-af38-54b73f5b2868
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 61e4ea81da1e8f31cabd7c2dae6ca5dc3251eef8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31106670"
---
# <a name="idebugdefaultport2getserver"></a>IDebugDefaultPort2::GetServer
Tato metoda získá rozhraní na server, který tento port je na.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetServer(  
   IDebugCoreServer3** ppServer  
);  
```  
  
```csharp  
int GetServer(  
   out IDebugCoreServer3 ppServer  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppServer`  
 [out] Vrátí implementaci objektu [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md) rozhraní.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md) je implementováno modulem Visual Studio a představuje server, který port se nachází na.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)