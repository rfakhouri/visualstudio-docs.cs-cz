---
title: Dialogové okno Příkazový řádek události před sestavením / po sestavení
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cs.ProjectPropertiesBuildEventsBuilder
- vb.ProjectPropertiesBuildEventsBuilder
helpviewer_keywords:
- $(SolutionExt)
- $(ProjectDir)
- $(TargetPath)
- $(ProjectExt)
- $(TargetFileName)
- $(PlatformName)
- $(SolutionName)
- macros, build events
- $(SolutionPath)
- $(ProjectPath)
- $(ProjectFileName)
- $(DevEnvDir)
- $(TargetName)
- $(TargetDir)
- $(SolutionDir)
- $(TargetExt)
- $(OutDir)
- $(ConfigurationName)
- $(SolutionFileName)
- $(ProjectName)
- build events, macros
ms.assetid: d49b2c57-24bf-4fb2-8351-5c4b6cca938f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 977bd72b478d2106f687d3666aad574a63ca68ec
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59656970"
---
# <a name="pre-build-eventpost-build-event-command-line-dialog-box"></a>Dialogové okno Příkazový řádek události před sestavením/po sestavení
Můžete zadat před nebo po sestavení událostí [stránka události sestavení, Návrhář projektu (C#)](../../ide/reference/build-events-page-project-designer-csharp.md) přímo v úpravách pole, nebo ho můžete vybrat makra před instrumentací a po sestavení ze seznamu dostupných maker.

> [!NOTE]
> Události před sestavením nebudou spuštěny, pokud je aktuální projekt a není aktivováno žádné sestavení.

## <a name="ui-element-list"></a>Seznam prvků uživatelského rozhraní
 **Pole pro úpravy příkazového řádku**

 Obsahuje události, které chcete spustit pro před sestavením nebo po sestavení.

> [!NOTE]
> Přidat `call` než vše post-build příkazy, které spouštějí soubory .bat. Například `call C:\MyFile.bat` nebo `call C:\MyFile.bat call C:\MyFile2.bat`.

 **Makra**

 Rozbalí textové pole k zobrazení seznamu maker vložit do textového pole pro příkazový řádek.

 **Tabulky – makro**

 Obsahuje seznam dostupná makra a její hodnotu. Popis jednotlivých naleznete v tématu makra níže. Můžete vybrat pouze jedno makro najednou k vložení do textového pole příkazového řádku.

 **Vložit**

 Vložení informací do příkazového řádku textové pole – makro vybraný v tabulce – makro.

### <a name="macros"></a>Makra
 Můžete použít některý z těchto maker určit umístění pro soubory, nebo chcete-li získat skutečný název výstupního souboru v případě více výběrů. Tato makra nerozlišují malá a velká písmena.

|– Makro|Popis|
|-----------|-----------------|
|`$(ConfigurationName)`|Název aktuální konfigurace projektu, například "Debug".|
|`$(OutDir)`|Cesta k adresáři výstupního souboru relativní vzhledem k adresáři projektu. To se přeloží na hodnotu pro vlastnost výstupní adresář. Její součástí zpětné lomítko na konci "\\".|
|`$(DevEnvDir)`|Instalační adresář sady Visual Studio (definované s jednotku a cestu); zahrnuje koncové lomítko "\\".|
|`$(PlatformName)`|Název aktuální cílové platformy. Například "AnyCPU".|
|`$(ProjectDir)`|Adresář projektu (definované s jednotku a cestu); zahrnuje koncové lomítko "\\".|
|`$(ProjectPath)`|Absolutní cesta název projektu (definované s diskovou jednotku, základním názvem a příponou).|
|`$(ProjectName)`|Základní název projektu.|
|`$(ProjectFileName)`|Název souboru projektu (definované s základní příponu názvu souboru).|
|`$(ProjectExt)`|Přípona souboru projektu. Zahrnuje "." před příponu souboru.|
|`$(SolutionDir)`|Adresář řešení (definované s jednotku a cestu); zahrnuje koncové lomítko "\\".|
|`$(SolutionPath)`|Absolutní cesta název řešení (definované s diskovou jednotku, základním názvem a příponou).|
|`$(SolutionName)`|Základní název řešení.|
|`$(SolutionFileName)`|Název souboru řešení (definované s základní příponu názvu souboru).|
|`$(SolutionExt)`|Přípona souboru řešení. Zahrnuje "." před příponu souboru.|
|`$(TargetDir)`|Adresář primárního výstupního souboru pro sestavení (definuje se jednotku a cestu). Její součástí zpětné lomítko na konci "\\".|
|`$(TargetPath)`|Absolutní cesta název primárního výstupního souboru pro sestavení (definuje se jednotky, cesty, základním názvem a příponou).|
|`$(TargetName)`|Základní název primárního výstupního souboru pro sestavení.|
|`$(TargetFileName)`|Název souboru primárního výstupního souboru pro sestavení (definované jako základní příponu názvu souboru).|
|`$(TargetExt)`|Přípona primárního výstupního souboru pro sestavení. Zahrnuje "." před příponu souboru.|

## <a name="see-also"></a>Viz také

- [Specifikace vlastních událostí sestavení v sadě Visual Studio](../../ide/specifying-custom-build-events-in-visual-studio.md)
- [Stránka Události sestavení, Návrhář projektu (C#)](../../ide/reference/build-events-page-project-designer-csharp.md)
- [Postupy: Určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)
- [Postupy: Určení událostí sestavení (C#)](../../ide/how-to-specify-build-events-csharp.md)