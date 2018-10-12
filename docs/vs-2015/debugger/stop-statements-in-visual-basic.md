---
title: Příkazy Stop v jazyce Visual Basic | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
helpviewer_keywords:
- End statements
- breakpoints, Stop statements
- debugging managed code, Stop statements vs breakpoints
- Stop statements, about Stop statements
- debugging [Visual Basic], Stop statements vs. breakpoints
ms.assetid: 4ad3fe5c-3dfb-4913-b2eb-a0b635751c18
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 45752b6b33a68e785dd9de028bd5c3de2930e964
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49261908"
---
# <a name="stop-statements-in-visual-basic"></a>Příkazy Stop v jazyce Visual Basic
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Příkaz Zastavit jazyka Visual Basic poskytuje programový alternativu k nastavením zarážky. Pokud ladicí program narazí příkaz Stop, přeruší spuštění programu (přejde do režimu přerušení). Programátoři v C# lze dosáhnout pomocí volání do System.Diagnostics.Debugger.Break stejný účinek.  
  
 Nastavení nebo odebrání příkazu Stop pomocí úpravy zdrojového kódu. Nelze nastavit nebo zrušte příkazech Stop pomocí příkazů ladicího programu, jako byste zarážku.  
  
 Na rozdíl od příkazem End příkaz Stop nepodporuje obnovení proměnné ani vrátit do režimu návrhu. Pokračovat můžete vybrat z nabídky ladění bude moct být spuštěná aplikace.  
  
 Při spuštění aplikace v jazyce Visual Basic vně ladicího programu, příkazu Stop se spuštění ladicího programu, pokud Just-in-Time je povoleno ladění. Pokud Just-in-Time není povoleno ladění, příkaz Stop se chová jako by šlo příkazem End ukončení provádění. Žádné QueryUnload nebo uvolnění události dojde, proto musíte odebrat všechny příkazy Stop z verze aplikace Visual Basic. Další informace najdete v tématu [ladění za běhu](../debugger/just-in-time-debugging-in-visual-studio.md).  
  
 Aby se nemusela odebrání příkazech Stop, můžete použít Podmíněná kompilace:  
  
```  
#If DEBUG Then  
   Stop  
#Else  
   ' Don't stop  
#End If  
```  
  
 Další možností je použití příkazu Assert místo příkazu Stop. Debug.Assert – příkaz zruší spuštění, jenom když je zadaná podmínka není splněna a automaticky odstraní při sestavení verze pro vydání. Další informace najdete v tématu [kontrolní výrazy ve spravovaného kódu](../debugger/assertions-in-managed-code.md). Pokud chcete kontrolní příkaz, který se vždy přeruší provádění v ladicí verzi, můžete to provést:  
  
```  
Debug.Assert(false)  
```  
  
 Ještě další možností je použít metodu Debug.Fail:  
  
```  
Debug.Fail("a clever output string goes here")  
```  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [C#, F # a typy projektů jazyka Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Ladění spravovaného kódu](../debugger/debugging-managed-code.md)



