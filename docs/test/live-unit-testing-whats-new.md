---
title: Co je nového v Live Unit Testing
ms.date: 10/11/2017
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing
- Live Unit Testing What's New
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
ms.openlocfilehash: 95cbdeb9a4e8a3f98fefa7650b36cc4dd59ed550
ms.sourcegitcommit: 87d7123c09812534b7b08743de4d11d6433eaa13
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/01/2019
ms.locfileid: "57221538"
---
# <a name="whats-new-in-live-unit-testing"></a>Novinky funkce Live Unit Testing

Toto téma obsahuje seznam nových funkcí pro Live Unit Testing v každé verzi sady Visual Studio od verze Visual Studio 2017 verze 15.3. Přehled o tom, jak používat Live Unit Testing, naleznete v tématu [pomocí sady Visual Studio Live Unit Testing](live-unit-testing.md).

## <a name="whats-new-in-live-unit-testing-for-visual-studio-2017-version-154"></a>Co je nového v Live Unit Testing pro Visual Studio 2017 verze 15.4

Od verze Visual Studio 2017 verze 15.4, Live Unit Testing obsahuje vylepšení v různých oblastech:

- **Vylepšené možnosti rozpoznání**. Pro uživatele, kteří neznáte, které Live Unit Testing funkce existuje, integrovaném vývojovém prostředí sady Visual Studio zobrazuje zlatý pruh, který uvádí Live Unit Testing pokaždé, když uživatel otevře řešení, která obsahuje testy jednotek, ale Live Unit Testing není povolená. Informace uváděné v zlatý pruh umožňuje uživateli získat další informace o Live Unit Testing a chcete ho povolit. Zlatý pruh také zobrazí informace, pokud Live Unit Testing požadavky nejsou splněny. Zde jsou některé z nich:

   - Adaptéry testu nebyly nalezeny.
   - Starší verze adaptéry testu jsou k dispozici.
   - Je potřeba obnovit balíčky NuGet odkazované řešení.

- **Integrace s oznámeními Centrum úkolů**. Integrované vývojové prostředí sady Visual Studio teď zobrazují Live Unit Testing zpracování na pozadí oznámení v centru úloh tak, aby uživatelé mohli snadno určit, co se děje při zapnuté funkci Live Unit Testing. To řeší klíče problém spouští se Live Unit Testing na velkých projektech. Dříve pár minut dokud ikony pokrytí objevily, uživatelé nelze určit, jestli se ve skutečnosti povolená Live Unit Testing a určuje, zda byla práce. Už ne.

- **Podpora pro MSTest verze 1 framework**: Live Unit Testing už spolupracuje s tři testovací architektury oblíbených částí: xUnit, NUnit a MSTest. Dříve Live Unit Testing pouze spolupráci při použití MS Test version 2 projektů testů jednotek MSTest. Od verze Visual Studio 2017 verze 15.4, teď podporuje také MSTest verze 1 i.

- **Spolehlivost a výkon**: Live Unit Testing nyní zajistí, že systém můžete lépe rozpoznat, kdy se projekty nebyly dokončeny načítání plně a zabraňuje padá Live Unit Testing. Výkon sestavení vylepšení také vyhnout reevaluating projekty MSBuild, když systém ví, že nic v projektu soubor se změnil.

- **Různé uživatelské rozhraní upřesnění**:  Matoucí **Live nastavit Test – zahrnout/vyloučit** gesta kliknutí pravým tlačítkem na možnost byl přejmenován na **Live Unit Testing Include/Exclude**. **Resetování čištění** možnost **testovací** > **Live Unit Testing** nabídky se odebrala. Je teď dostupné tak, že vyberete **nástroje** > **možnosti** > **Live Unit Testing** a vyberete **odstranit trvalá Data** .

## <a name="whats-new-in-live-unit-testing-for-visual-studio-2017-version-153"></a>Co je nového v Live Unit Testing pro Visual Studio 2017 verze 15.3

Od verze Visual Studio 2017 verze 15.3, Live Unit Testing vylepšení funkcí a vylepšení v dvě hlavní oblasti:

- Podpora .NET Core a .NET Standard. Live Unit Testing můžete použít na .NET Core a .NET Standard řešeními napsanými v jazyce C# nebo Visual Basic.

- Byl vylepšen výkon. Můžete si všimnout, že výkon je výrazně rychlejší po první celé sestavení a spuštění testů v rámci Live Unit Testing. Všimněte si také významné výkonnostní zlepšení v následných spustí z Live Unit Testing ve stejném řešení. Jsme teď uchování dat vygenerovaných vašimi Live Unit Testing a znovu ji co nejlépe s aktuální kontroly použít.

Kromě těchto hlavními dodatky Live Unit Testing zahrnuje následující vylepšení:

- Nová ikona kádinky se teď používá k rozlišení testovací metodu z běžné metody. Ikona prázdný kádinky označuje, že konkrétní test není zahrnutý v Live Unit Testing.

- Když kliknete na testovací metodu se v místním okně uživatelského rozhraní pokrytí ikony Live Unit Testing, máte nyní možnost ladit test přímo z daného kontextu okna uživatelského rozhraní a bez nutnosti opustit editor kódu. To je užitečné, když se díváte selhání testu.

- Bylo přidáno několik dalších možností konfigurovatelné nástroje/Možnosti/Live Unit Testing / Obecné. Můžete limit paměti používané pro Live Unit Testing. Můžete také zadat cestu k souboru trvalých dat. Live Unit Testing pro otevřené řešení.

- Bylo přidáno několik další položky nabídky v části do nabídky panelu z testu/Live Unit Testing. **Resetovat Vyčistit** trvalá data odstraní a znovu se generuje. **Možnost** přejde k nástroje/Možnosti/Live Unit Testing / Obecné.

- Následující atributy můžete nyní použít k určení ve zdrojovém kódu, že chcete vyloučit z Live Unit Testing cílové testovací metody:

   - Pro xUnit: `[Trait("Category", "SkipWhenLiveUnitTesting")]`
   - Pro NUnit: `[Category("SkipWhenLiveUnitTesting")]`
   - Pro MSTest: `[TestCategory("SkipWhenLiveUnitTesting")]`

## <a name="see-also"></a>Viz také:

- [Představení funkce Live Unit Testing](live-unit-testing-intro.md)
- [Live Unit Testing pomocí sady Visual Studio](live-unit-testing.md)
