---
title: Volání událostí ladicího programu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], events
ms.assetid: b3440ac3-80af-40c6-bef4-cbf00fa67885
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6a24c661c986116d9966d2ca5785bd51e2726c6d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54998401"
---
# <a name="call-debugger-events"></a>Volání událostí ladicího programu
Dojde k událostem v ladicími relacemi v určitém pořadí.  
  
## <a name="discussion"></a>Diskuse  
 Pro pochopení způsobu volání mezi ladicího stroje (DE) a správce ladění relace (SDM), představuje následující pořadí volání události, ke kterým dochází v typické ladicí relace:  
  
1.  [Připojení a odpojení programu](../../extensibility/debugger/attaching-and-detaching-to-a-program.md)  
  
2.  [Spuštění ladicího programu](../../extensibility/debugger/launching-the-debugger.md)  
  
3.  [Ukončení programu](../../extensibility/debugger/terminating-a-program.md)  
  
4.  [Vytvořením zarážky](../../extensibility/debugger/creating-a-breakpoint.md)  
  
5.  [Když vytvoří vazbu zarážky nebo stát nevázaných](../../extensibility/debugger/when-a-breakpoint-binds-or-becomes-unbound.md)  
  
6.  [Chyby zarážky](../../extensibility/debugger/breakpoint-errors.md)  
  
7.  [Dosažení zarážky](../../extensibility/debugger/hitting-a-breakpoint.md)  
  
8.  [Odstranění zarážky](../../extensibility/debugger/deleting-a-breakpoint.md)  
  
9. [Přechod do režimu přerušení](../../extensibility/debugger/entering-break-mode.md)  
  
10. [Krokování v režimu pozastavení](../../extensibility/debugger/stepping-in-break-mode.md)  
  
11. [Vyhodnocení výrazu v režimu pozastavení](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
12. [Zpracování výjimek](../../extensibility/debugger/exception-handling-visual-studio-sdk.md)  
  
## <a name="see-also"></a>Viz také:  
 [Vytvoření vlastního ladicího stroje](../../extensibility/debugger/creating-a-custom-debug-engine.md)