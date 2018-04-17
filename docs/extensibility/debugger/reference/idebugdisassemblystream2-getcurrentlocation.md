---
title: IDebugDisassemblyStream2::GetCurrentLocation | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugDisassemblyStream2::GetCurrentLocation
helpviewer_keywords:
- IDebugDisassemblyStream2::GetCurrentLocation
ms.assetid: 512302f1-12b1-4107-8a6e-c5bc878ce1c3
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a8c76adbeee7086e28b7673a9eb1a90bb8b9650c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugdisassemblystream2getcurrentlocation"></a>IDebugDisassemblyStream2::GetCurrentLocation
Vrátí identifikátor umístění kód, který představuje aktuální umístění v kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetCurrentLocation(   
   UINT64* puCodeLocationId  
);  
```  
  
```csharp  
int GetCurrentLocation(   
   out ulong puCodeLocationId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `puCodeLocationId`  
 [out] Vrátí identifikátor umístění kódu. Naleznete v části poznámky [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md) metoda popis identifikátor umístění kódu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Identifikátor umístění kódu můžete převést na kontext kódu voláním [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)