---
title: 'Postupy: přechod zpět na funkci, která volala MFC při zastavení | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.mfc
dev_langs:
- CSharp
- VB
- FSharp
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: da15793027eb643078771d33464258fea73fec9d
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283389"
---
# <a name="how-to-get-back-to-the-function-that-called-mfc-if-halted"></a>Postupy: Přechod zpět na funkci, která volala MFC při zastavení.
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte nastavení importu a exportu v nabídce Nástroje. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](../ide/personalizing-the-visual-studio-ide.md).  
  
 Pokud jste použili **přerušit** příkaz **ladění** nabídky k zastavení programu skončila v prostředí MFC a jste si jisti, že problém je ve vašem kódu, okno zásobníku volání můžete přejít zpět na funkci. Další informace najdete v tématu [postupy: použití okna zásobník volání](../debugger/how-to-use-the-call-stack-window.md).  
  
 V některých případech může váš kód proniknout pumpu zpráv. V zásobníku volání v takovém případě neexistuje žádný uživatelský kód. K tomuto problému vyhnout, můžete používat zarážky (případně s stavy a počty přístupů) místo **přerušit** příkazu. Další informace najdete v tématu [zarážky a sledované body](https://msdn.microsoft.com/library/fe4eedc1-71aa-4928-962f-0912c334d583).  
  
### <a name="to-navigate-to-the-function-from-which-mfc-was-called"></a>Přejít na funkce, ze kterého byla volána knihovny MFC  
  
-   Použití **zásobník volání** okna.  
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu nejčastější dotazy](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)