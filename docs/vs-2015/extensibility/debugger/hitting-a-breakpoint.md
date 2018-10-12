---
title: Dosažení zarážky | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], hitting breakpoints
- breakpoints, hitting
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a4b5805621d1fd58f6c5d39c779e6b87719edac6
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49214978"
---
# <a name="hitting-a-breakpoint"></a>Dosažení zarážky
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Následující část popisuje proces při ladicího stroje (DE) narazí na zarážku při spuštění nebo při krokování:  
  
## <a name="troubleshooting-a-hit-breakpoint"></a>Řešení potíží s průchodů zarážky  
  
1.  Odešle DE [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) rozhraní jako **EVENT_SYNC_STOP**.  
  
2.  Správce ladění relace (SDM) volá [IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) zobrazíte, které bylo dosaženo zarážky.  
  
## <a name="see-also"></a>Viz také  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)

