---
title: IDebugAddress2::GetProcessID | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugAddress2::GetProcessID
helpviewer_keywords:
- IDebugAddress2::GetProcessID method
ms.assetid: 2c18889d-074a-4b95-87b4-bf1a067f44ed
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 999ac618ff3656d4aea1fc96cc0b54427d55e285
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53822713"
---
# <a name="idebugaddress2getprocessid"></a>IDebugAddress2::GetProcessID
Načte ID procesu, který vlastní objekt reprezentovaný tímto objektem [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md) rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetProcessID (  
   DWORD* pProcID  
);  
```  
  
```csharp  
int GetProcessID (  
   out uint pProcID  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pProcID`  
 [out] ID procesu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDebugAddress2](../../../extensibility/debugger/reference/idebugaddress2.md)