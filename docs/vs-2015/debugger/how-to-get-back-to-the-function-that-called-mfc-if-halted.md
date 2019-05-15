---
title: 'Postupy: Vrátit zpět na funkci, která volala MFC při zastavení | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.mfc
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- functions [C++], debugging
- function calls, returning to calling function
- debugging [MFC], returning to calling function
- debugging [MFC], functions
- Break command
- programs, halting
- functions [debugger]
ms.assetid: d254a5a9-afbd-4923-9d7a-7422d824cabf
caps.latest.revision: 21
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c19cbf6e892ba8b35f2b92ad9b86aa0b74a64810
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65685887"
---
# <a name="how-to-get-back-to-the-function-that-called-mfc-if-halted"></a>Postupy: Vrátit zpět na funkci, která volala MFC při zastavení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

POZNÁMKA:]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte nastavení importu a exportu v nabídce Nástroje. Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 Pokud jste použili **přerušit** příkaz **ladění** nabídky k zastavení programu skončila v prostředí MFC a jste si jisti, že problém je ve vašem kódu, okno zásobníku volání můžete přejít zpět na funkci. Další informace najdete v tématu [jak: Použijte okno zásobníku volání](../debugger/how-to-use-the-call-stack-window.md).  
  
 V některých případech může váš kód proniknout pumpu zpráv. V zásobníku volání v takovém případě neexistuje žádný uživatelský kód. K tomuto problému vyhnout, můžete používat zarážky (případně s stavy a počty přístupů) místo **přerušit** příkazu. Další informace najdete v tématu [zarážky a sledované body](https://msdn.microsoft.com/fe4eedc1-71aa-4928-962f-0912c334d583)).  
  
### <a name="to-navigate-to-the-function-from-which-mfc-was-called"></a>Přejít na funkce, ze kterého byla volána knihovny MFC  
  
- Použití **zásobník volání** okna.  
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu nejčastější dotazy](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)
