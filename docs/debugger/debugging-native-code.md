---
title: Ladění nativního kódu | Microsoft Docs
ms.custom: ''
ms.date: 04/11/2017
ms.technology: vs-ide-debug
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
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: f57f1e559452c64f9f1a7b019d75b52384081d65
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="debugging-native-code"></a>Ladění nativního kódu
V části jsou popsané některé běžné problémy ladění a techniky pro nativní aplikace. Techniky popsané v této části jsou nejdůležitější techniky. Mechanismů používání ladicího programu sady Visual Studio, najdete v části [ladicí program plán](../debugger/debugger-basics.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Postupy: ladění optimalizovaného kódu](../debugger/how-to-debug-optimized-code.md)  
 Poskytuje tipy k ladění optimalizovaného kódu, konkrétně, proč ladíte neoptimalizované verzi vašeho programu, výchozí nastavení optimalizace pro konfigurace Debug a Release a tipy pro vyhledávání chyb, které se zobrazují pouze v (zapnete optimalizovaný kód Optimalizace v konfiguraci sestavení ladění).  
  
 [DebugBreak a __debugbreak](../debugger/debugbreak-and-debugbreak.md)  
 Popisuje Win32 `DebugBreak` funkce a obsahuje odkaz na jeho referenční téma v sadě SDK pro platformu. Také popisuje `__debugbreak` vnitřní.  
  
 [Kontrolní výrazy jazyka C/C++](../debugger/c-cpp-assertions.md)  
 Popisuje assertion příkazy, funkce, výhody použití je (zachycení logické chyby, Kontrola výsledků operace a testování chybové stavy), jejich interakci s `_DEBUG`a typy kontrolních výrazů v podporované [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 [Postupy: ladění vnořeného kódu sestavení](../debugger/how-to-debug-inline-assembly-code.md)  
 Poskytuje možnosti pro krátké pokyny týkající se použití okna zpětného překladu Chcete-li zobrazit pokyny sestavení a okna registry, chcete-li zobrazit obsah registru a poskytuje odkazy na témata týkající se těchto windows.  
  
 [Techniky ladění MFC](../debugger/mfc-debugging-techniques.md)  
 Odkazy na ladění techniky pro MFC programy, včetně: nevracení afxdebugbreak –, makro trasování, zjišťování paměti v prostředí MFC MFC kontrolní výrazy a zmenšení velikosti MFC ladění sestavení.  
  
 [Techniky ladění CRT](../debugger/crt-debugging-techniques.md)  
 Halda ladění odkazy k ladění techniky pro knihovnu C Run-Time, včetně pomocí ladění knihovny CRT, makra pro vytváření sestav, rozdíly mezi malloc – a _malloc_dbg –, zápis ladění funkce háku a CRT.  
  
 [Nativní kód nejčastější dotazy k ladění](../debugger/debugging-native-code-faqs.md)  
 Poskytuje odpovědi na nejčastější dotazy týkající se ladění programy Visual C++  
  
 [COM a prvků ActiveX ladění](../debugger/com-and-activex-debugging.md)  
 Obsahuje informace o ladění aplikací modelu COM a prvků ActiveX, včetně nástrojů, které můžete použít pro model COM a prvků ActiveX ladění.  
  
 [Postupy: ladění vloženého kódu](../debugger/how-to-debug-injected-code.md)  
 Obsahuje pokyny k ladění kódu, který používá atributy. Pokyny zahrnují zapnutí zdrojové poznámky, jak zobrazit vloženého kódu a jak zobrazit zpětný překlad kódu k aktuálnímu bodu provádění.  
  
 [Návod: Ladění paralelní aplikace](../debugger/walkthrough-debugging-a-parallel-application.md)  
 Popisuje postup použití **paralelních úloh** a **paralelní zásobníky** nástroje systému windows k ladění paralelní aplikace.  
  
## <a name="related-sections"></a>Související oddíly  
 [Typy projektů Visual C++](../debugger/debugging-preparation-visual-cpp-project-types.md)  
 Obsahuje odkazy na témata, které popisují, jak k ladění nativního projektu typy vytvořené šablony projektů Visual C++.  

 [Ladění projektů knihovny DLL](../debugger/debugging-dll-projects.md) poskytuje informace o tom, jak ladit nativní a spravovaná knihovny DLL.
  
 [Prohlídka funkce ladicí program](../debugger/debugger-feature-tour.md)  
 Obsahuje odkazy na větší části ladění dokumentaci. Obsahuje informace, co je nového v ladicí program, nastavení a příprava, zarážky, zpracování výjimek, upravit a pokračovat, ladění spravovaného kódu, ladění nativního kódu, ladění SQL a odkazy na uživatelské rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečení ladicího programu](../debugger/debugger-security.md)  
 [Ladění v sadě Visual Studio](../debugger/index.md) [prohlídka funkce ladicího programu](../debugger/debugger-feature-tour.md)