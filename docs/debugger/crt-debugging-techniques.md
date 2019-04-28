---
title: Techniky ladění CRT | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- c.runtime.debugging
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [CRT]
- CRT, debugging
- debugging [C++], CRT debug support
ms.assetid: 9be561f6-14a8-44ff-925d-d911d5b8e6ff
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 88cdc78fd739de412b4cf796d0ca7a42f9174e0a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62564031"
---
# <a name="crt-debugging-techniques"></a>Techniky ladění CRT
Pokud ladíte program, který používá knihovny run-time jazyka C, může být užitečné tyto techniky ladění.

## <a name="in-this-section"></a>V tomto oddílu
 [Použití knihovny ladění CRT](../debugger/crt-debug-library-use.md)

 Popisuje podporu ladění poskytovaných knihovnou Run-Time jazyka C a poskytuje pokyny pro přístup k nástroji.

 [Makra pro vytváření sestav](../debugger/macros-for-reporting.md)

 Poskytuje informace o **_RPTn** a **_RPTFn** makra (definovaná v CRTDBG. H), který nahradí použití `printf` příkazy pro ladění.

 [Ladění verzí funkcí přidělení haldy](../debugger/debug-versions-of-heap-allocation-functions.md)

 Tento článek popisuje zvláštní ladění verzí funkcí přidělení haldy, včetně: jak CRT mapuje volání, výhody volání je explicitně, jak se vyhnout převod sledování samostatné typy přidělení v blocích klienta a výsledky není definování _ LADĚNÍ.

 [Podrobnosti haldy ladění CRT](../debugger/crt-debug-heap-details.md)

 Obsahuje odkazy na správu paměti a halda ladění, typy bloků na haldě ladění pomocí haldy ladění, stavu haldy funkce generování sestav a sledování požadavků na přidělení haldy.

 [Zápis funkce volání pro ladění](../debugger/debug-hook-function-writing.md)

 Seznamy odkazů na klientský blok integrovat funkce, funkce háku přidělení, háky přidělení a přidělení paměti CRT a funkce háku sestavy.

 [Hledání nevrácené paměti pomocí knihovny CRT](../debugger/finding-memory-leaks-using-the-crt-library.md)

 Popisuje postupy pro zjištění a izolace nevrácené paměti pomocí ladicího programu a knihovny jazyka C Run-Time.

## <a name="related-sections"></a>Související oddíly

- [Ladění nativního kódu](../debugger/debugging-native-code.md) – Tento článek popisuje některé běžné problémy ladění a techniky pro aplikace C a C++.
- [Zabezpečení ladicího programu](../debugger/debugger-security.md) – poskytuje doporučení pro zabezpečení ladění.