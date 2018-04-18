---
title: Dialogové okno Příkazový řádek události sestavení Post pro události před sestavením | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e020bd0dde446d12232779410a12d569ecc2395c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="pre-build-eventpost-build-event-command-line-dialog-box"></a>Dialogové okno Příkazový řádek události před sestavením/po sestavení
Můžete zadat před nebo po sestavení událostí [stránka události sestavení, Návrhář projektu (C#)](../../ide/reference/build-events-page-project-designer-csharp.md) přímo v úpravy pole, nebo ho můžete vybrat makra před a po sestavení ze seznamu dostupných makra.  
  
> [!NOTE]
>  Události před sestavením se nespustí, pokud je aktuální projekt a není aktivováno žádné sestavení.  
  
## <a name="ui-element-list"></a>Seznam prvků uživatelského rozhraní  
 **Příkazový řádek textové pole**  
 Obsahuje události, které chcete spustit buď před sestavením nebo po sestavení.  
  
> [!NOTE]
>  Přidat `call` příkaz před příkazy všechny po sestavení, které spouštějí .bat soubory. Například `call C:\MyFile.bat` nebo `call C:\MyFile.bat call C:\MyFile2.bat`.  
  
 **Makra**  
 Rozšíří textové pole pro zobrazení seznamu maker vložit do textového pole pro příkazový řádek.  
  
 **Tabulka – makro**  
 Zobrazuje seznam dostupných makra a jeho hodnotu. Makra níže najdete popis každého. Můžete vybrat pouze jedno makro současně vložení do textového pole pro příkazový řádek.  
  
 **Vložení**  
 Vloží do příkazového řádku úprav makro v tabulce makro.  
  
### <a name="macros"></a>Makra  
 Zadejte umístění pro soubory nebo chcete-li získat skutečný název souboru vstupního souboru v případě více výběrů můžete tyto makra. Tyto makra nerozlišují malá a velká písmena.  
  
|– Makro|Popis|  
|-----------|-----------------|  
|`$(ConfigurationName)`|Název aktuální konfigurací projektu, například "Debug".|  
|`$(OutDir)`|Cesta k adresáři výstupního souboru, relativně k adresáři projektu. To se přeloží na hodnotu pro vlastnost výstupního adresáře. Obsahuje koncové zpětné lomítko,\\'.|  
|`$(DevEnvDir)`|Instalační adresář sady Visual Studio (definovanou s jednotku a cestu); zahrnuje koncové zpětné lomítko,\\'.|  
|`$(PlatformName)`|Název aktuální cílové platformy. Například "AnyCPU".|  
|`$(ProjectDir)`|Do adresáře projektu (s jednotku a cestu definovanou); zahrnuje koncové zpětné lomítko,\\'.|  
|`$(ProjectPath)`|Absolutní cesta název projektu (definovanou s jednotky, cesta, základní název a příponu souboru).|  
|`$(ProjectName)`|Základní název projektu.|  
|`$(ProjectFileName)`|Název souboru projektu (definovanou s základní název a soubor rozšíření).|  
|`$(ProjectExt)`|Přípona souboru projektu. Obsahuje,., před příponu souboru.|  
|`$(SolutionDir)`|Adresář řešení (definovanou s jednotku a cestu); zahrnuje koncové zpětné lomítko,\\'.|  
|`$(SolutionPath)`|Absolutní cesta název řešení (definovanou s jednotky, cesta, základní název a příponu souboru).|  
|`$(SolutionName)`|Základní název řešení.|  
|`$(SolutionFileName)`|Název souboru řešení (definovanou s základní název a soubor rozšíření).|  
|`$(SolutionExt)`|Přípona souboru řešení. Obsahuje,., před příponu souboru.|  
|`$(TargetDir)`|Adresář primárního výstupního souboru pro sestavení (definovanou s jednotku a cestu). Obsahuje koncové zpětné lomítko,\\'.|  
|`$(TargetPath)`|Absolutní cesta název primárního výstupního souboru pro sestavení (definovanou s jednotky, cesta, základní název a příponu souboru).|  
|`$(TargetName)`|Základní název primárního výstupního souboru pro sestavení.|  
|`$(TargetFileName)`|Název souboru primárního výstupního souboru pro sestavení (definován jako základní název a soubor rozšíření).|  
|`$(TargetExt)`|Přípona souboru primárního výstupního souboru pro sestavení. Obsahuje,., před příponu souboru.|  
  
## <a name="see-also"></a>Viz také  
 [Specifikace vlastních událostí sestavení v sadě Visual Studio](../../ide/specifying-custom-build-events-in-visual-studio.md)   
 [Stránka události sestavení, Návrhář projektu (C#)](../../ide/reference/build-events-page-project-designer-csharp.md)   
 [Postupy: určení událostí sestavení (Visual Basic)](../../ide/how-to-specify-build-events-visual-basic.md)   
 [Postupy: Specifikace událostí sestavení (C#)](../../ide/how-to-specify-build-events-csharp.md)