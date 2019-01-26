---
title: IDebugProcess3 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProcess3
helpviewer_keywords:
- IDebugProcess3 interface
ms.assetid: 7bd6b952-cf34-4e66-b8f6-d472dac3748f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bca432c7999d4ec3e7ff4a5a8700eea698486798
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54962794"
---
# <a name="idebugprocess3"></a>IDebugProcess3
Toto rozhraní představuje spuštěného procesu a jeho programy. Toto rozhraní existuje jako náhrada do několika metod v [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní. To umožňuje řídit všechny programy v procesu.  
  
> [!NOTE]
>  [Pokračovat](../../../extensibility/debugger/reference/idebugprogram2-continue.md), [Execute](../../../extensibility/debugger/reference/idebugprogram2-execute.md), a [krok](../../../extensibility/debugger/reference/idebugprogram2-step.md) metody jsou zastaralé a už musí být použity. Použít metody odpovídající na `IDebugProcess3` místo toho rozhraní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProcess3 : IDebugProcess2  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní je implementováno port. Tento vlastní port dodavatele pro správu programů jako skupinu. Když programy se spravují jako skupiny, můžete řídit jejich spuštění a navázání jazyk pro vyhodnocovače výrazů. Toto rozhraní musí být implementované dodavatele portu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je volán primárně správce ladění relace (SDM) aby bylo možné pracovat se skupinou programy uvedené v tomto procesu.  
  
 Volání [QueryInterface](/cpp/atl/queryinterface) na [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) rozhraní k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Kromě metod zděděných z [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md), `IDebugProcess3` implementuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Continue](../../../extensibility/debugger/reference/idebugprocess3-continue.md)|Pokračuje v provádění nebo krokování procesem.|  
|[Execute](../../../extensibility/debugger/reference/idebugprocess3-execute.md)|Zahájí vykonávání procesu.|  
|[Step](../../../extensibility/debugger/reference/idebugprocess3-step.md)|Kroky dál jedna instrukce nebo příkaz v procesu.|  
|[GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)|Získá z důvodu, že proces byl spuštěn pro ladění.|  
|[SetHostingProcessLanguage](../../../extensibility/debugger/reference/idebugprocess3-sethostingprocesslanguage.md)|Nastaví hostování jazyk tak, aby načíst vyhodnocovací filtr výrazů odpovídající ladicí stroj.|  
|[GetHostingProcessLanguage](../../../extensibility/debugger/reference/idebugprocess3-gethostingprocesslanguage.md)|Získá jazyk pro tento proces aktuálně nastavená.|  
|[DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)|Zakáže upravit a pokračovat (ENC) pro tento proces.<br /><br /> Dodavatel port. Tento vlastní port neimplementuje této metody (vždy by měl vrátit `E_NOTIMPL`).|  
|[GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md)|Získání stavu KODÉRU pro tento proces.<br /><br /> Dodavatel port. Tento vlastní port neimplementuje této metody (vždy by měl vrátit `E_NOTIMPL`).|  
|[GetEngineFilter](../../../extensibility/debugger/reference/idebugprocess3-getenginefilter.md)|Načte pole jedinečné identifikátory pro dostupné ladicí stroj.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)