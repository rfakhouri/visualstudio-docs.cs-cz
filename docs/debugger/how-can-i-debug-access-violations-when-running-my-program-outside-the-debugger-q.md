---
title: Ladění narušení přístupu při spuštění aplikace mimo ladicí program | Dokumentace Microsoftu
ms.custom: seodec18
ms.date: 11/04/2016
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
ms.openlocfilehash: 8b65c10b07b93e657a9e3cb9da5f94d5c9b14362
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53854019"
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Jak mohu ladit porušení přístupu, když program spouštím mimo ladicí program?

## <a name="problem-description"></a>Popis problému  
 Program lze spustit v prostředí sady Visual Studio bez problémů, ale při spuštění je samostatný s operačním systémem Windows, vytváří narušení přístupu. Jak mohu ladit tento problém?  
  
## <a name="solution"></a>Řešení  
 Nastavte [Just-in-time ladění](../debugger/just-in-time-debugging-in-visual-studio.md) možnost a spusťte svůj program samostatné, dokud dojde k narušení přístupu. Potom v **narušení přístupu** dialogové okno, můžete kliknout na **zrušit** spuštění ladicího programu.  
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu nejčastější dotazy](../debugger/debugging-native-code-faqs.md)   
 [Ladění nativního kódu](../debugger/debugging-native-code.md)