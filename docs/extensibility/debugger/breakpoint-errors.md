---
title: "Breakpoint – chyby | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- breakpoints, errors
- debugging [Debugging SDK], breakpoint errors
- errors [Debugging SDK]
ms.assetid: 79221c6b-a924-4c8e-a778-e312e4e0c0c8
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f9c197bbaf8fb79ea4396c7b2e36af94d59c7ea8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="breakpoint-errors"></a>Breakpoint – chyby
Následující popisuje proces, když se pokusí vytvořit vazbu na kód zarážku ale selže:  
  
## <a name="troubleshooting-a-breakpoint-error"></a>Řešení potíží s chybou zarážek  
  
1.  Modul ladění (DE) odešle [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md) pro relaci ladění správce (SDM).  
  
2.  Volání SDM [IDebugBreakpointErrorEvent2::GetErrorBreakpoint](../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md) (IDebugErrorBreakpoint2 ** `ppErrorBP`) získat zarážek chyby.  
  
3.  Volání SDM [IDebugErrorBreakpoint2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md) získat čekající zarážek, z něhož pochází zarážek chyby.  
  
4.  Volání SDM [IDebugErrorBreakpoint2::GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md) získat z důvodu, proč se nepodařilo vytvořit vazbu zarážek chyby.  
  
## <a name="see-also"></a>Viz také  
 [Události volání ladicí program](../../extensibility/debugger/calling-debugger-events.md)