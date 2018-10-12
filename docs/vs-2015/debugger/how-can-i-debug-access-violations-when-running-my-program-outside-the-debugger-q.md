---
title: Jak mohu ladit porušení přístupu, když program spouštím mimo ladicí program? | Dokumenty Microsoft
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
- vs.debug.access
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 486b981311d93a93866622ccf80b6eabdee748ff
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49290755"
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Jak mohu ladit porušení přístupu, když program spouštím mimo ladicí program?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Popis problému  
 Program lze spustit v prostředí sady Visual Studio bez problémů, ale při spuštění je samostatný s operačním systémem Windows, vytváří narušení přístupu. Jak mohu ladit tento problém?  
  
## <a name="solution"></a>Řešení  
 Nastavte [Just-in-time ladění](../debugger/just-in-time-debugging-in-visual-studio.md) možnost a spusťte svůj program samostatné, dokud dojde k narušení přístupu. Potom v **narušení přístupu** dialogové okno, můžete kliknout na **zrušit** spuštění ladicího programu.  
  
 Také najdete v článku znalostní báze Knowledge Base Q133174, "Jak najít, kde dochází k chybu obecné ochrany (zásady skupiny)." Články znalostní báze můžete vyhledat na disku CD knihovny MSDN nebo tak, že [ http://support.microsoft.com/ ](http://support.microsoft.com/).  
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu nejčastější dotazy](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)



