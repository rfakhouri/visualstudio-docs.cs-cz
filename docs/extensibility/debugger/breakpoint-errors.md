---
title: Chyby zarážky | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- breakpoints, errors
- debugging [Debugging SDK], breakpoint errors
- errors [Debugging SDK]
ms.assetid: 79221c6b-a924-4c8e-a778-e312e4e0c0c8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ea48e83034a02f4c99bb1d9de03db0ee1b371281
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55038419"
---
# <a name="breakpoint-errors"></a>Chyby zarážky
Následující popisuje proces, když se pokusí vytvořit vazbu na kód zarážku ale selže.  
  
## <a name="troubleshoot-a-breakpoint-error"></a>Chyby zarážky  
  
1.  Ladicí stroj (DE) odešle [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md) do Správce ladění relace (SDM).  
  
2.  Volání SDM [IDebugBreakpointErrorEvent2::GetErrorBreakpoint](../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md) (IDebugErrorBreakpoint2 ** `ppErrorBP`) zobrazíte Chyba zarážky.  
  
3.  Volání SDM [IDebugErrorBreakpoint2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md) zobrazíte čekající zarážka, ze kterého pochází chyba zarážky.  
  
4.  Volání SDM [IDebugErrorBreakpoint2::GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md) zobrazíte důvod, proč se nepodařilo vytvořit vazbu zarážky chyb.  
  
## <a name="see-also"></a>Viz také:  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)