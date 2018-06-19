---
title: IDebugPort2::GetPortRequest | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: 6897c3085f14be785e4baaace0de7a4e92fea9ae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31114778"
---
# <a name="idebugport2getportrequest"></a>IDebugPort2::GetPortRequest
Získá Popis portu, který byl dříve používán k vytvoření port (Pokud je k dispozici).  
  
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
 [out] Vrátí [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) objektu, který představuje požadavek, který byl použit k vytvoření port.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  Vrátí `E_PORT_NO_REQUEST` Pokud port nebyl vytvořen pomocí [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md) port požadavku.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)   
 [IDebugPortRequest2](../../../extensibility/debugger/reference/idebugportrequest2.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)