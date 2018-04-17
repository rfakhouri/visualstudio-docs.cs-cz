---
title: Jak mohu ladit porušení přístupu, když program spouštím mimo ladicí program? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.access
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- access violation debugging
- debugging [Visual Studio], access violations
ms.assetid: 780a298a-132e-4245-8370-8c82ca27c6c1
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9f3e4a79ba90f887f11c3fd9a7bddf318ace35cc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Jak mohu ladit porušení přístupu, když program spouštím mimo ladicí program?
## <a name="problem-description"></a>Popis problému  
 Program lze spustit v prostředí Visual Studio dobře, ale při opakovaném spuštění samostatné s operačním systémem Windows, vyvolá porušení přístupu. Jak mohu ladit tento problém?  
  
## <a name="solution"></a>Řešení  
 Nastavte [pouze za běhu ladění](../debugger/just-in-time-debugging-in-visual-studio.md) možnost a spusťte svůj program samostatné, dokud dojde k porušení přístupu. Potom v **narušení přístupu** dialogové okno, můžete kliknout na **zrušit** spuštění ladicího programu.  
  
## <a name="see-also"></a>Viz také  
 [Nativní kód nejčastější dotazy k ladění](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)