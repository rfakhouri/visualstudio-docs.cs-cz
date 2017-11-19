---
title: IDebugProgram2::EnumCodePaths | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugProgram2::EnumCodePaths
helpviewer_keywords: IDebugProgram2::EnumCodePaths
ms.assetid: fb100c3c-9c29-4d63-bd1f-a3e531cb395f
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d9aec7791092d8e3c531bf9ad0cb6f50d3d8ab22
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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