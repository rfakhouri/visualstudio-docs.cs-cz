---
title: IDebugProgram2::EnumCodePaths | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::EnumCodePaths
helpviewer_keywords:
- IDebugProgram2::EnumCodePaths
ms.assetid: fb100c3c-9c29-4d63-bd1f-a3e531cb395f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 56cc9580ec2e434066d1c0a3ce674a4111e433af
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugprogram2enumcodepaths"></a>IDebugProgram2::EnumCodePaths
Načte seznam cesty kódu pro dané pozici ve zdrojovém souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumCodePaths(   
   LPCOLESTR            pszHint,  
   IDebugCodeContext2*  pStart,  
   IDebugStackFrame2*   pFrame,  
   BOOL                 fSource,  
   IEnumCodePaths2**    ppEnum,  
   IDebugCodeContext2** ppSafety  
);  
```  
  
```csharp  
int EnumCodePaths(   
   string                 pszHint,  
   IDebugCodeContext2     pStart,  
   IDebugStackFrame2      pFrame,  
   Int                    fSource,  
   out IEnumCodePaths2    ppEnum,  
   out IDebugCodeContext2 ppSafety  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszHint`  
 [v] Aplikace word v části kurzor v **zdroj** nebo **zpětný překlad** zobrazení v rozhraní IDE.  
  
 `pStart`  
 [v] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objektu, který představuje aktuální kontext kódu.  
  
 `pFrame`  
 [v] [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) objekt reprezentující rámce zásobníku přidružené k aktuální zarážek.  
  
 `fSource`  
 [v] Nenulové hodnoty (`TRUE`) Pokud se v **zdroj** zobrazení nebo nula (`FALSE`) Pokud se v **zpětný překlad** zobrazení.  
  
 `ppEnum`  
 [out] Vrátí [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md) objekt obsahující seznam cesty kódu.  
  
 `ppSafety`  
 [out] Vrátí [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) objekt reprezentující kontextu další kód nastavit jako zarážky v případě, že zvolený code cesta bude přeskočena. Tomu může dojít v případě zkratována logický výraz, např.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Cesta kódu popisuje název metody nebo funkce, která byla volána potřebujete k aktuálnímu bodu při provádění tohoto programu. Seznam cesty kódu představuje zásobníku volání.  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IEnumCodePaths2](../../../extensibility/debugger/reference/ienumcodepaths2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)