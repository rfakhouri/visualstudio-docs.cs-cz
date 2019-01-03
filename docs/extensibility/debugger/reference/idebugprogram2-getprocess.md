---
title: IDebugProgram2::GetProcess | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::GetProcess
helpviewer_keywords:
- IDebugProgram2::GetProcess
ms.assetid: 1d602485-ebaf-451c-9165-f2e226f20a90
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0da808fc2c23fd7d5d5daeb86b6c062a8fe012ad
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53985404"
---
# <a name="idebugprogram2getprocess"></a>IDebugProgram2::GetProcess
Získáte, na kterém tento program běží v procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetProcess(  
   IDebugProcess2** ppProcess  
);  
```  
  
```csharp  
int GetProcess(  
   out IDebugProcess2 ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ppProcess`  
 [out] Vrátí [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) rozhraní, které představuje proces.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud ladicí stroj (DE) implementuje [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md) rozhraní, je DE implementace této metody by měla vždy vrátit `E_NOTIMPL` protože Zavedenými nedokáže určit, který proces běží v aplikaci a proto nelze splňovat implementace této metody.  
  
 Implementace `IDebugEngineLaunch2` rozhraní znamená, že je DE musí vědět, jak vytvořit proces; proto, Německo provádění [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) je schopen vědět, jaký proces běží v rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)