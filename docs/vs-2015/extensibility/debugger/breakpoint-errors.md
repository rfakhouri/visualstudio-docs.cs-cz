---
title: Chyby zarážky | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- breakpoints, errors
- debugging [Debugging SDK], breakpoint errors
- errors [Debugging SDK]
ms.assetid: 79221c6b-a924-4c8e-a778-e312e4e0c0c8
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 656f96a344e3d527407cd5a91b0a5910e1e6005c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667372"
---
# <a name="breakpoint-errors"></a>Chyby zarážky
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [chyby zarážky](https://docs.microsoft.com/visualstudio/extensibility/debugger/breakpoint-errors).  
  
Následující popisuje proces, když se pokusí vytvořit vazbu na kód zarážku ale selže:  
  
## <a name="troubleshooting-a-breakpoint-error"></a>Řešení potíží s chybou zarážku  
  
1.  Ladicí stroj (DE) odešle [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md) do Správce ladění relace (SDM).  
  
2.  Volání SDM [IDebugBreakpointErrorEvent2::GetErrorBreakpoint](../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md) (IDebugErrorBreakpoint2 ** `ppErrorBP`) zobrazíte Chyba zarážky.  
  
3.  Volání SDM [IDebugErrorBreakpoint2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md) zobrazíte čekající zarážka, ze kterého pochází chyba zarážky.  
  
4.  Volání SDM [IDebugErrorBreakpoint2::GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md) zobrazíte důvod, proč se nepodařilo vytvořit vazbu zarážky chyb.  
  
## <a name="see-also"></a>Viz také  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)

