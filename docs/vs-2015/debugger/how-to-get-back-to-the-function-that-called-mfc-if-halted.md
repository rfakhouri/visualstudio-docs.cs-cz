---
title: 'Postupy: přechod zpět na funkci, která volala MFC při zastavení | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
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
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9cf717fec6324d26d2f483bd0f38c3a0731f0d67
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49172923"
---
# <a name="how-to-get-back-to-the-function-that-called-mfc-if-halted"></a>Postupy: Přechod zpět na funkci, která volala MFC při zastavení.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

POZNÁMKA:]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte nastavení importu a exportu v nabídce Nástroje. Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 Pokud jste použili **přerušit** příkaz **ladění** nabídky k zastavení programu skončila v prostředí MFC a jste si jisti, že problém je ve vašem kódu, okno zásobníku volání můžete přejít zpět na funkci. Další informace najdete v tématu [postupy: použití okna zásobník volání](../debugger/how-to-use-the-call-stack-window.md).  
  
 V některých případech může váš kód proniknout pumpu zpráv. V zásobníku volání v takovém případě neexistuje žádný uživatelský kód. K tomuto problému vyhnout, můžete používat zarážky (případně s stavy a počty přístupů) místo **přerušit** příkazu. Další informace najdete v tématu [zarážky a sledované body](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)).  
  
### <a name="to-navigate-to-the-function-from-which-mfc-was-called"></a>Přejít na funkce, ze kterého byla volána knihovny MFC  
  
-   Použití **zásobník volání** okna.  
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu nejčastější dotazy](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)



