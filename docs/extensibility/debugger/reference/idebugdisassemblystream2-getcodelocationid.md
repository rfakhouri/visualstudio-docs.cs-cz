---
title: IDebugDisassemblyStream2::GetCodeLocationId | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugDisassemblyStream2::GetCodeLocationId
helpviewer_keywords:
- IDebugDisassemblyStream2::GetCodeLocationId
ms.assetid: 567adfb8-2f54-499a-a027-e4ecb82277ef
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 52423c671bb27de0c5b03a302dc757cad7a3aaa1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53891515"
---
# <a name="idebugdisassemblystream2getcodelocationid"></a>IDebugDisassemblyStream2::GetCodeLocationId
Vrátí identifikátor umístění kódu pro kontext kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetCodeLocationId(   
   IDebugCodeContext2* pCodeContext,  
   UINT64*             puCodeLocationId  
);  
```  
  
```csharp  
int GetCodeLocationId(   
   IDebugCodeContext2 pCodeContext,  
   out ulong          puCodeLocationId  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pCodeContext`  
 [in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objektu, který chcete převést na identifikátor.  
  
 `puCodeLocationId`  
 [out] Vrátí identifikátor umístění kódu. Viz poznámky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_CODE_CONTEXT_OUT_OF_SCOPE` Pokud kontextu kód je platný, ale mimo obor.  
  
## <a name="remarks"></a>Poznámky  
 Identifikátor umístění kódu je specifický pro ladicí stroj (DE) podporuje zpětný překlad. Tento identifikátor umístění se používá interně DE ke sledování pozice v kódu a je obvykle adresa nebo posun určitého druhu. Jediným požadavkem je, že pokud kontext kódu z jednoho umístění je menší než kontext kódu z jiného umístění, pak odpovídající identifikátor umístění kódu první kontext kódu musí také být menší než identifikátor umístění kódu druhý kontext kódu.  
  
 Chcete-li načíst kód kontextu identifikátor umístění kódu, zavolejte [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentContext2](../../../extensibility/debugger/reference/idebugdocumentcontext2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetCodeContext](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodecontext.md)