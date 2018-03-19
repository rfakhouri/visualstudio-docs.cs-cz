---
title: "Co je nového v za provozu testování částí | Microsoft Docs"
ms.date: 10-11-2017
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing
- Live Unit Testing What's New
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
ms.openlocfilehash: 5f979970b926e3a1a3d0ef7aee53f1e71e7fc0dc
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="whats-new-in-live-unit-testing"></a>Co je nového v za provozu testování částí

Toto téma obsahuje seznam nových funkcí přidán do Live testování částí v jednotlivých verzí sady Visual Studio od verze Visual Studio 2017 verze 15.3. Přehled o tom, jak používat Live testování částí v tématu [Live testování částí s Visual Studio 2017](live-unit-testing.md).

## <a name="whats-new-in-live-unit-testing-for-visual-studio-2017-version-154"></a>Co je nového v za provozu pro Visual Studio 2017 verzi 15.4 testování částí

Od verze Visual Studio 2017 verzi 15.4, Live jednotkové testování obsahuje vylepšení a vylepšení v různých oblastech:

- **Vylepšené možnosti rozpoznání**. Pro uživatele, kteří neznáte, které za provozu jednotky testování funkce existuje, Visual Studio IDE zobrazuje gold panel, který uvádí Live testování částí vždy, když uživatel otevře řešení, které zahrnuje testování částí, ale za provozu testování jednotky není povoleno. Informace uvedené v panelu gold umožňuje uživateli, další informace o Live testování částí a povolit. Gold panelu zobrazí také informace, pokud Live testování částí požadavky nejsou splněny. Mezi ně patří:

   - Test adaptéry chybí.
   - Starší verze testovací adaptéry jsou k dispozici.
   - Obnovení balíčků NuGet odkazuje řešení je potřeba. 

- **Integrace s oznámeními Centrum úkolů**. Visual Studio IDE zobrazí pozadí Live testování částí zpracování oznámení o centra úloh tak, aby uživatelé mohli snadno určit, co se děje, pokud je povoleno Live testování částí. To řeší problém klíče od Live testování částí v velké řešení. Dříve po několika minutách dokud ikony pokrytí zobrazovaly, uživatelé se nepodařilo určit Určuje, jestli byl skutečně povolená Live testování částí a jestli se správně. Není už!

- **Podpora pro Mstestu framework verze 1**: Live testování částí již pracuje s tři testování architektury oblíbených jednotka: xUnit NUnit a Mstestu. Dříve Live jednotkové testování pouze práce při použití Mstestu projektů testování částí MS Test version 2. Od verze Visual Studio 2017 verzi 15.4, teď také podporuje Mstestu také verze 1. 

- **Spolehlivost a výkon**: Live testování částí teď zajišťuje, že systém může lépe rozpoznat, kdy projekty nedokončili načítání plně a zabraňuje chybám Live testování částí. Sestavení výkonu vylepšení také vyhnout reevaluating projektů MSBuild při systému ví, že nic v projektu soubor byl změněn.  

- **Různé uživatelské rozhraní obecnější**: složitá **Live nastavit testovací – zahrnout nebo vyloučit** možnost gesto klikněte pravým tlačítkem byl přejmenován na **Live jednotky testování vložit/vyloučit**. **Resetovat Vyčistit** možnost **Test**, **Live testování částí** nabídky byla odebrána. Je nyní dostupné výběrem **nástroje**, **možnosti**, **Live testování částí** a výběrem **odstranit Data trvalé**.

## <a name="whats-new-in-live-unit-testing-for-visual-studio-2017-version-153"></a>Co je nového v za provozu pro Visual Studio 2017 verze 15.3 testování částí

Od verze Visual Studio 2017 verze 15.3, Live testování částí vylepšení funkcí a vylepšení v dvě hlavní oblasti:

- Podpora pro .NET Core a .NET Standard. Můžete za provozu jednotkové testování na .NET Core a .NET Standard řešení, které jsou napsané v C# nebo Visual Basic.
 
-  Vylepšení výkonu. Můžete si všimnout, že výkonu je výrazně rychlejší po první úplné sestavení a spuštění testů v za provozu testování jednotky. Také můžete si všimnout výrazné zvýšení výkonu při následné spustí Live testování částí na stejném řešení. Jsme teď zachovat data generována Live testování částí a co nejvíce s aktuální kontroly jej znovu použít. 
 
Kromě těchto hlavní dodatky Live jednotkové testování obsahuje následující vylepšení: 

- Nová ikona kádinky je teď použít k rozlišení metoda testu z běžné metody. Ikona prázdný kádinky označuje, že konkrétní test není zahrnutý v za provozu testování jednotky. 

- Když kliknete na testovací metoda z okna automaticky otevírané okno uživatelského rozhraní ikony pokrytí Live testování částí, máte nyní možnost ladění test přímo na tomto kontextu v okně uživatelského rozhraní a aniž by museli opustit editor kód. Toto je obzvláště užitečná, když hledáte v testu se nezdařila.  

- Několik dalších konfigurovatelné možnosti přidané k nástroje/Možnosti/živé jednotky testování nebo Obecné. Můžete cap paměť použitá pro Live testování jednotky. Cesta k souboru trvalých dat. Live testování částí můžete také zadat otevřete řešení. 

- V nabídce panelu z testu nebo živé jednotky testování bylo přidáno několik položek nabídky Další. **Resetování Vyčistit** odstraní trvalých dat a znovu ho generuje. **Možnost** přejde k nástroje/Možnosti/živé jednotky testování nebo Obecné.
  
- Následující atributy teď můžete zadat ve zdrojovém kódu, které chcete vyloučit cílové testovací metody ze za provozu testování částí:
   - Pro xUnit: `[Trait("Category", "SkipWhenLiveUnitTesting")]`
   - Pro NUnit: `[Category("SkipWhenLiveUnitTesting")]`
   - Pro Mstestu: `[TestCategory("SkipWhenLiveUnitTesting")]`

## <a name="see-also"></a>Viz také
[Představení za provozu testování částí](live-unit-testing-intro.md)   
[Testování částí pomocí Visual Studio 2017 za provozu](live-unit-testing.md)

