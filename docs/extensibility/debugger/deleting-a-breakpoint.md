---
title: Odstranění zarážky | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- breakpoints, deleting
- debugging [Debugging SDK], deleting breakpoints
ms.assetid: 75a046cc-d20a-4c79-ad2d-1f18426ac5d0
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 7551ee12993780544bbb9c9eb127a9bfb4364e8d
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66345831"
---
# <a name="deleting-a-breakpoint"></a>Odstranění zarážky
Následující část popisuje proces při odstraňování čekající zarážkou:

## <a name="deletion-process"></a>Proces odstraňování
 Správce ladění relace (SDM) volá [IDebugPendingBreakpoint2::Delete](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md) metoda odebrání čekající zarážka a všechny vazby zarážky vázán z něj.

> [!NOTE]
> Jeden vázaná zarážka může také odstranit volání [IDebugBoundBreakpoint2::Delete](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md).

## <a name="see-also"></a>Viz také:
- [Volání událostí ladicího programu](../../extensibility/debugger/calling-debugger-events.md)