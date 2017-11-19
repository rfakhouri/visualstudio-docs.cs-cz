---
title: IDebugEngine2::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine2::Attach
helpviewer_keywords: IDebugEngine2::Attach
ms.assetid: 173dcbda-5019-4c5e-bca9-a071838b5739
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7c31e4c8367c1ceba5a4692438e8c1f1503f4f63
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugengine2attach"></a>IDebugEngine2::Attach
Připojí modul ladění (DE) pro program nebo programy. Volá se správcem ladicí relace (SDM), když je DE je spuštěné v procesu na SDM.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Attach(   
   IDebugProgram2**      pProgram,  
   IDebugProgramNode2**  rgpProgramNodes,  
   DWORD                 celtPrograms,  
   IDebugEventCallback2* pCallback,  
   ATTACH_REASON         dwReason  
);  
```  
  
```csharp  
int Attach(   
   IDebugProgram2[]     pProgram,  
   IDebugProgramNode2[] rgpProgramNodes,  
   uint                 celtPrograms,  
   IDebugEventCallback2 pCallback,  
   Enum_ATTACH_REASON   dwReason  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pProgram`  
 [v] Pole [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) objekty, které představují programy, připojí se k. Jedná se o programy portu.  
  
 `rgpProgramNodes`  
 [v] Pole [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) objekty, které představují program uzly, jeden pro každý program. Program uzly v toto pole představují stejnou programy jako v `pProgram`. Program uzly jsou uvedeny tak, aby je DE můžete identifikovat programy pro připojení k.  
  
 `celtPrograms`  
 [v] Počet programy a program uzlech v `pProgram` a `rgpProgramNodes` pole.  
  
 `pCallback`  
 [v] [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) objekt, který chcete použít k odesílání událostí ladění na SDM.  
  
 `dwReason`  
 [v] Hodnota z [ATTACH_REASON](../../../extensibility/debugger/reference/attach-reason.md) výčet, který určuje důvod připojení těchto programů. Další informace najdete v části poznámky.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Existují tři důvody pro připojení k programu, následujícím způsobem:  
  
-   `ATTACH_REASON_LAUNCH`Označuje, že DE je připojení k programu, protože uživatel spustí proces, který jej obsahuje.  
  
-   `ATTACH_REASON_USER`Označuje, že uživatel má explicitně DE připojit k programu (nebo proces, který obsahuje program).  
  
-   `ATTACH_REASON_AUTO`Označuje, že je DE je připojení na konkrétní aplikaci, protože ji už je ladění další programy v určitém procesu. To se označuje taky jako automatické připojení.  
  
 Když tato metoda je volána, DE musí poslat tyto události v pořadí:  
  
1.  [IDebugEngineCreateEvent2](../../../extensibility/debugger/reference/idebugenginecreateevent2.md) (pokud nebyl již odeslán pro konkrétní instanci modul ladění)  
  
2.  [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md)  
  
3.  [IDebugLoadCompleteEvent2](../../../extensibility/debugger/reference/idebugloadcompleteevent2.md)  
  
 Kromě toho, pokud je z důvodu pro připojení `ATTACH_REASON_LAUNCH`, musí poslat DE [IDebugEntryPointEvent2](../../../extensibility/debugger/reference/idebugentrypointevent2.md) událostí.  
  
 Jednou získá DE [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) objektu odpovídající program probíhá ladění, může být dotazován pro všechny privátní rozhraní.  
  
 Před voláním metody program uzlu v poli poskytují `pProgram` nebo `rgpProgramNodes`, zosobnění, pokud je to nutné, by měla být povolená na `IDebugProgram2` rozhraní, které představuje uzel program. Za normálních okolností však tento krok není nutné. Další informace najdete v tématu [problémy se zabezpečením](../../../extensibility/debugger/security-issues.md).  
  
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