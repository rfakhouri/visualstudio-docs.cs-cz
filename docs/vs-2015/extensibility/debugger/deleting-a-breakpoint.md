---
title: Odstranění zarážky | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- breakpoints, deleting
- debugging [Debugging SDK], deleting breakpoints
ms.assetid: 75a046cc-d20a-4c79-ad2d-1f18426ac5d0
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9a70cfe5b728cc9af019752bd0c9c9d2f5105043
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54772176"
---
# <a name="deleting-a-breakpoint"></a>Odstranění zarážky
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Následující část popisuje proces při odstraňování čekající zarážkou:  
  
## <a name="deletion-process"></a>Proces odstraňování  
 Správce ladění relace (SDM) volá [IDebugPendingBreakpoint2::Delete](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md) metoda odebrání čekající zarážka a všechny vazby zarážky vázán z něj.  
  
> [!NOTE]
>  Jeden vázaná zarážka může také odstranit volání [IDebugBoundBreakpoint2::Delete](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md).  
  
## <a name="see-also"></a>Viz také  
 [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)
