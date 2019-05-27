---
title: Ladění narušení přístupu při spuštění aplikace mimo ladicí program
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
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d42dd206117885a23a6c1c15c712be4dc4cd8fe2
ms.sourcegitcommit: 13ab9a5ab039b070b9cd9251d0b83dd216477203
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66177675"
---
# <a name="how-can-i-debug-access-violations-when-running-my-program-outside-the-debugger"></a>Jak mohu ladit porušení přístupu, když program spouštím mimo ladicí program?

## <a name="problem-description"></a>Popis problému
 Program lze spustit v prostředí sady Visual Studio bez problémů, ale při spuštění je samostatný s operačním systémem Windows, vytváří narušení přístupu. Jak mohu ladit tento problém?

## <a name="solution"></a>Řešení
 Nastavte [Just-in-time ladění](../debugger/just-in-time-debugging-in-visual-studio.md) možnost a spusťte svůj program samostatné, dokud dojde k narušení přístupu. Potom v **narušení přístupu** dialogové okno, můžete kliknout na **zrušit** spuštění ladicího programu.

## <a name="see-also"></a>Viz také
- [Nejčastější dotazy k ladění nativního kódu](../debugger/debugging-native-code-faqs.md)
- [Ladění nativního kódu](../debugger/debugging-native-code.md)