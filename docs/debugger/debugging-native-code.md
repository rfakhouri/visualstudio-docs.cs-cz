---
title: Ladění nativního kódu | Dokumentace Microsoftu
ms.date: 04/11/2017
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging native code
- debugging [C++], native code
- debugging [Visual Studio], native code
- native code, debugging
ms.assetid: d94eee90-7e0d-4cac-88c1-9831030daa5e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 5a7cf0b150c45037941010bf7e611f4bc21252c7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62851906"
---
# <a name="debugging-native-code"></a>Ladění nativního kódu
Část popisuje některé běžné problémy ladění a techniky pro nativní aplikace. Techniky popsané v této části jsou techniky vysoké úrovně. Mechanismy pomocí ladicího programu sady Visual Studio, naleznete v tématu [nejdřív se podívejte na ladicí program](../debugger/debugger-feature-tour.md)).

## <a name="in-this-section"></a>V tomto oddílu
 [Postupy: Ladění optimalizovaného kódu](../debugger/how-to-debug-optimized-code.md) poskytuje tipy pro ladění optimalizovaného kódu, konkrétně, proč by měl ladit neoptimalizované verzi aplikace, nastavení optimalizace výchozí konfigurace Debug a Release a tipy pro hledání chyb, který pouze Zobrazit v optimalizovaném kódu (zapnutí optimalizace v konfiguraci sestavení ladění).

 [DebugBreak a __debugbreak](../debugger/debugbreak-and-debugbreak.md) popisuje Win32 `DebugBreak` fungovat a získáte odkaz na jeho referenční téma v sadě SDK platformy. Také popisuje `__debugbreak` vnitřní.

 [Kontrolní výrazy jazyka C/C++](../debugger/c-cpp-assertions.md) popisuje příkazy kontrolního výrazu, jak fungují, výhody používání jejich (zachycení logických chyb, Kontrola výsledků operace a testování chybové stavy), jejich interakce s `_DEBUG`a typy kontrolní výrazy, které jsou podporovány v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

 [Postupy: Ladění vnořeného kódu sestavení](../debugger/how-to-debug-inline-assembly-code.md) poskytuje obsah krátké pokyny týkající se použití okna zpětného překladu zobrazíte pokyny k sestavení a okno registrů, chcete-li zobrazit registru a obsahuje odkazy na témata týkající se těchto systému windows.

 [Techniky ladění MFC](../debugger/mfc-debugging-techniques.md) odkazy na postupy pro programy MFC, včetně ladění: nevracení afxdebugbreak – makro trasování, zjišťování paměti v knihovně MFC, knihovny MFC kontrolní výrazy a nezmenšit velikost této knihovny MFC ladění sestavení.

 [Techniky ladění CRT](../debugger/crt-debugging-techniques.md) odkazy na ladění techniky pro knihovny Run-Time jazyka C, včetně použití ladění knihovny CRT, makra pro vytváření sestav, rozdíly mezi malloc a _malloc_dbg zápis funkce háku ladění a haldy ladění CRT.

 [Ladění nativního kódu nejčastější dotazy k](../debugger/debugging-native-code-faqs.md) poskytuje odpovědi na nejčastější dotazy týkající se ladění programy v jazyce Visual C++

 [COM a ActiveX ladění](../debugger/com-and-activex-debugging.md) poskytuje informace o ladění aplikace modelu COM a ActiveX, včetně nástroje, které můžete použít pro model COM a ActiveX ladění.

 [Postupy: Ladění vloženého kódu](../debugger/how-to-debug-injected-code.md) obsahuje pokyny k ladění kódu, který používá atributy. Pokyny zahrnují zapnutí zdrojové poznámky, jak zobrazit vloženého kódu a jak zobrazit zpětný překlad kódu v aktuální bod provádění.

 [Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md) popisuje způsob použití **paralelní úlohy** a **paralelní zásobníky** nástroje windows pro ladění paralelní aplikace.

## <a name="related-sections"></a>Související oddíly
 [Typy projektů Visual C++](../debugger/debugging-preparation-visual-cpp-project-types.md) obsahuje odkazy na témata, která popisují, jak ladit nativní projekt typy vytvořené šablony projektů Visual C++.

 [Ladění projektů knihovny DLL](../debugger/debugging-dll-projects.md) poskytuje informace o tom, jak ladit nativní a spravované knihovny DLL.

 [Nejdřív se podívejte na ladicí program](../debugger/debugger-feature-tour.md) obsahuje odkazy na větší části dokumentace ladění. Obsahuje informace, co je nového v ladicím programu, nastavení a příprava, zarážky, zpracování výjimek, upravit a pokračovat, ladění spravovaného kódu, ladění nativního kódu, ladění SQL a odkazy na uživatelské rozhraní.

## <a name="see-also"></a>Viz také

- [Zabezpečení ladicího programu](../debugger/debugger-security.md)
- [Ladění v sadě Visual Studio](../debugger/index.md)