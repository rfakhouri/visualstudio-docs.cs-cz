---
title: Breakpoint – chyby | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- breakpoints, errors
- debugging [Debugging SDK], breakpoint errors
- errors [Debugging SDK]
ms.assetid: 79221c6b-a924-4c8e-a778-e312e4e0c0c8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3e3c7271cc573388231045143f275d1032bef437
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31099880"
---
# <a name="breakpoint-errors"></a>Breakpoint – chyby
Následující popisuje proces, když se pokusí vytvořit vazbu na kód zarážku ale selže:  
  
## <a name="troubleshooting-a-breakpoint-error"></a>Řešení potíží s chybou zarážek  
  
1.  Modul ladění (DE) odešle [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md) pro relaci ladění správce (SDM).  
  
2.  Volání SDM [IDebugBreakpointErrorEvent2::GetErrorBreakpoint](../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md) (IDebugErrorBreakpoint2 ** `ppErrorBP`) získat zarážek chyby.  
  
3.  Volání SDM [IDebugErrorBreakpoint2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md) získat čekající zarážek, z něhož pochází zarážek chyby.  
  
4.  Volání SDM [IDebugErrorBreakpoint2::GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md) získat z důvodu, proč se nepodařilo vytvořit vazbu zarážek chyby.  
  
## <a name="see-also"></a>Viz také  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)