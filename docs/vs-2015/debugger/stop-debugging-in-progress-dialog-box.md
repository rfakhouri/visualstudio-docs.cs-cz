---
title: Zastavit ladění do dialogového okna průběhu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.stopnow
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- SQL
- VB
- CSharp
- C++
helpviewer_keywords:
- Stop Debugging in Progress dialog box
ms.assetid: ed7ef49d-e25f-4a4d-9396-9bc7b4143117
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c29754937d3b1ff7f4c44fc87929d84844743387
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54788122"
---
# <a name="stop-debugging-in-progress-dialog-box"></a>Dialogové okno Ukončit probíhající ladění
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Toto dialogové okno se zobrazí, když ladicí program se pokouší zastavit ladicí relace, ale zastavuje se relace je, že přejdete na nějakou dobu trvat. Zastavuje se relace ladění je obvykle velmi rychlý a toto dialogové okno se nezobrazí. V některých případech však trvá určitou dobu trvat odpojit od všech procesů, který se právě ladí. Zastavuje se relace trvá déle než několik sekund (nebo pokud dojde k chybě odpojení), zobrazí se toto dialogové okno. Pokud k tomu dochází často, může být kvůli internímu problému a můžete chtít obraťte se na oddělení technické podpory.  
  
 Počkejte procesy, které chcete odpojit a toto dialogové okno zmizí, nebo použijte **Zastavit** tlačítko vynutit okamžité ukončení.  
  
 **Zastavit nyní**  
 Kliknutím na toto tlačítko k ukončení relace ladění okamžitě. Pomocí **Zastavit**bude ukončen, spíše než odpojování procesů, který se právě ladí. Pokud ladíte systémové procesy, ukončuje se tyto procesy s **Zastavit** může mít neočekávané a nežádoucí účinky.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)   
 [Odpojuje se programy](http://msdn.microsoft.com/f2c756c2-8079-474b-94c2-01c19a141a01)
