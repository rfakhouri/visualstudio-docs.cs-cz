---
title: "Volání metody události ladicí program | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: debugging [Debugging SDK], events
ms.assetid: b3440ac3-80af-40c6-bef4-cbf00fa67885
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3acccf7233e62ca45d450a5e33c21a286ca4a204
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="calling-debugger-events"></a>Události volání ladicí program
Při ladění relace k událostem v určitém pořadí.  
  
## <a name="discussion"></a>Diskusní  
 Zjistit vzor volání mezi modul ladění (DE) a správce ladicí relace (SDM) představuje následující pořadí volání události, které nastaly v typické ladicí relace:  
  
1.  [Připojení a odpojení programu](../../extensibility/debugger/attaching-and-detaching-to-a-program.md)  
  
2.  [Spuštění ladicího programu](../../extensibility/debugger/launching-the-debugger.md)  
  
3.  [Ukončení programu](../../extensibility/debugger/terminating-a-program.md)  
  
4.  [Vytváření zarážky](../../extensibility/debugger/creating-a-breakpoint.md)  
  
5.  [Když zarážku váže nebo stal nevázaných](../../extensibility/debugger/when-a-breakpoint-binds-or-becomes-unbound.md)  
  
6.  [Breakpoint – chyby](../../extensibility/debugger/breakpoint-errors.md)  
  
7.  [Stiskne zarážky](../../extensibility/debugger/hitting-a-breakpoint.md)  
  
8.  [Odstranění zarážky](../../extensibility/debugger/deleting-a-breakpoint.md)  
  
9. [Přejít do režimu pozastavení](../../extensibility/debugger/entering-break-mode.md)  
  
10. [Krokování s v režimu pozastavení](../../extensibility/debugger/stepping-in-break-mode.md)  
  
11. [Vyhodnocení výrazu v režimu pozastavení](../../extensibility/debugger/expression-evaluation-in-break-mode.md)  
  
12. [Zpracování výjimek](../../extensibility/debugger/exception-handling-visual-studio-sdk.md)  
  
## <a name="see-also"></a>Viz také  
 [Vytváření vlastních ladění modulu](../../extensibility/debugger/creating-a-custom-debug-engine.md)