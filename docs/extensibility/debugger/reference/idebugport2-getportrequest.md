---
title: IDebugPort2::GetPortRequest | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPort2::GetPortRequest
helpviewer_keywords:
- IDebugPort2::GetPortRequest
ms.assetid: 14abf847-0675-4fa8-872e-971e00c84224
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7bc68272523100c07879b00b261b86f27023a13b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53844613"
---
# <a name="idebugport2getportrequest"></a>IDebugPort2::GetPortRequest
Získá Popis portu, který byl předtím použit k vytvoření portu (Pokud je k dispozici).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetPortRequest(   
   IDebugPortRequest2** ppRequest  
);  
```  
  
```csharp  
int GetPortRequest(   
   out IDebugPortRequest2 ppRequest  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppRequest`  
 [out] Vrátí [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) objekt představující žádost, která byla použita k vytvoření portu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  Vrátí `E_PORT_NO_REQUEST` Pokud port nebyl vytvořen pomocí [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) port požadavku.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)