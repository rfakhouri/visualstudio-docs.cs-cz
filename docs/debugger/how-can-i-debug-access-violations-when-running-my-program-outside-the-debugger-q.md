---
title: "Jak mohu ladit porušení přístupu, když program spouštím mimo ladicí program? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.access
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0af98932a940126c8f7288d7b5c830bb40f270fe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Jak mohu ladit porušení přístupu, když program spouštím mimo ladicí program?
## <a name="problem-description"></a>Popis problému  
 Program lze spustit v prostředí Visual Studio dobře, ale při opakovaném spuštění samostatné s operačním systémem Windows, vyvolá porušení přístupu. Jak mohu ladit tento problém?  
  
## <a name="solution"></a>Řešení  
 Nastavte [pouze za běhu ladění](../debugger/just-in-time-debugging-in-visual-studio.md) možnost a spusťte svůj program samostatné, dokud dojde k porušení přístupu. Potom v **narušení přístupu** dialogové okno, můžete kliknout na **zrušit** spuštění ladicího programu.  
  
 Také najdete v článku znalostní báze Knowledge Base Q133174, "Postup vyhledání, kde dochází k chybu obecné ochrany (zásady skupiny)." Můžete vyhledat články znalostní báze Knowledge Base na disku CD knihovny MSDN nebo tak, že [http://support.microsoft.com/](http://support.microsoft.com/).  
  
## <a name="see-also"></a>Viz také  
 [Nativní kód nejčastější dotazy k ladění](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)