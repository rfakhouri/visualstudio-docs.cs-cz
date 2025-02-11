---
title: IDebugEngine2::Attach | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngine2::Attach
helpviewer_keywords:
- IDebugEngine2::Attach
ms.assetid: 173dcbda-5019-4c5e-bca9-a071838b5739
caps.latest.revision: 15
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: a82d26fbfd6fe08f4976aaa7643bcaa95008032f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68196047"
---
# <a name="idebugengine2attach"></a>IDebugEngine2::Attach
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Připojí ladicí stroj (DE) pro program nebo programy. Když DE je spuštěné v rámci procesu SDM volány správce ladění relace (SDM).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT Attach(   
   IDebugProgram2**      pProgram,  
   IDebugProgramNode2**  rgpProgramNodes,  
   DWORD                 celtPrograms,  
   IDebugEventCallback2* pCallback,  
   ATTACH_REASON         dwReason  
);  
```  
  
```csharp  
int Attach(   
   IDebugProgram2[]     pProgram,  
   IDebugProgramNode2[] rgpProgramNodes,  
   uint                 celtPrograms,  
   IDebugEventCallback2 pCallback,  
   Enum_ATTACH_REASON   dwReason  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pProgram`  
 [in] Pole [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekty, které představují programy k bude připojený. Jedná se o programy portu.  
  
 `rgpProgramNodes`  
 [in] Pole [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) objekty, které představují program uzlů, jeden pro každou aplikaci. Uzly programů v tomto poli představují stejné programy jako v `pProgram`. Uzly programů jsou uvedeny tak, aby DE můžete identifikovat programy se připojit k.  
  
 `celtPrograms`  
 [in] Počet aplikací a program uzlech v `pProgram` a `rgpProgramNodes` pole.  
  
 `pCallback`  
 [in] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objekt, který se má použít k odesílání událostí ladění na SDM.  
  
 `dwReason`  
 [in] Hodnota z [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md) výčet, který je obsažený důvod připojení těchto programů. Další informace najdete v části poznámky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Existují tři důvody pro připojení k programu, následujícím způsobem:  
  
- `ATTACH_REASON_LAUNCH` Označuje, že je DE je připojení k programu, protože uživatel spustí proces, který jej obsahuje.  
  
- `ATTACH_REASON_USER` Označuje, že uživatel explicitně požaduje DE se připojit k programu (nebo proces, který obsahuje program).  
  
- `ATTACH_REASON_AUTO` Označuje, že je DE je připojení ke konkrétní programu, protože ji už ladí další programy v určitém procesu. To se také nazývá Automatické připojení.  
  
  Pokud tato metoda je volána, DE není potřeba tyto události odesílat v pořadí:  
  
1. [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md) (pokud ho už se neodeslala pro konkrétní instanci ladicí stroj)  
  
2. [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)  
  
3. [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)  
  
   Kromě toho, pokud je důvodem připojení `ATTACH_REASON_LAUNCH`, DE musí odeslat [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md) událostí.  
  
   Jednou získá DE [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) objektu odpovídající program laděn, je možné zadávat dotazy pro všechny privátní rozhraní.  
  
   Před voláním metody program uzlu v poli uvedena v každém `pProgram` nebo `rgpProgramNodes`, zosobnění, pokud je to nutné, by měla být povolená na `IDebugProgram2` rozhraní, které představuje uzel programu. Za normálních okolností však tento krok není nezbytný. Další informace najdete v tématu [problémy se zabezpečením](../../../extensibility/debugger/security-issues.md).  
  
## <a name="see-also"></a>Viz také  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md)   
 [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md)   
 [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)   
 [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)   
 [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md)
