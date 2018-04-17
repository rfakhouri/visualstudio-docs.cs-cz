---
title: Visual Studio příkazového řádku DEVENV | Microsoft Docs
ms.date: 02/28/2018
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- switches, Devenv
- command-line switches, Devenv
- command line [Visual Studio], switches
- Devenv
ms.assetid: e12bc6ed-74fd-4bea-8d7c-89b99c20bad8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3adde520b76de347da025c819ec39dce50660f2b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="devenv-command-line-switches"></a>Přepínače příkazového řádku nástroje devenv

DEVENV umožňuje nastavit různé možnosti pro integrované vývojové prostředí (IDE), a také vytvářet, ladit a nasadit projekty z příkazového řádku. Pomocí přepínače spouštět IDE ze skriptu nebo soubor .bat, například skript noční sestavení, nebo spuštění rozhraní IDE v konkrétní konfigurací.

> [!NOTE]
> O úlohách spojených s sestavení doporučujeme používat nástroje MSBuild místo devenv. Další informace najdete v tématu [reference k příkazovému řádku MSBuild](../../msbuild/msbuild-command-line-reference.md).

## <a name="devenv-switch-syntax"></a>Syntaxe přepínač nástroje devenv

Ve výchozím nastavení příkazy nástroje devenv předat nástroj devenv.com přepínače. Nástroj devenv.com poskytuje výstup prostřednictvím datových proudů standardní systému, například `stdout` a `stderr`. Nástroj určuje příslušné přesměrování vstupů/výstupů v případě zachycení výstup, třeba do souboru TXT.

Na druhé straně příkazy, které začínají `devenv.exe` můžete použít stejné přepínače, ale nástroj devenv.com přeskočí.

Syntaxe pravidla pro `devenv` přepínače vypadat podobně jako u jiných DOS nástroje příkazového řádku. Platí pro všechny následující syntaxe pravidla `devenv` přepínače a jejich argumenty:

- Příkazy začínat `devenv`.

- Přepínače nerozlišují malá a velká písmena.

- Při zadávání řešení nebo projektu, je prvním argumentem Název řešení soubor nebo soubor projektu, včetně cesta k souboru.

- Pokud první argument je soubor, který není projekt nebo řešení, tento soubor se otevře v editoru odpovídající v nové instanci rozhraní IDE.

- Pokud zadáte název souboru projektu místo názvu souboru řešení `devenv` příkaz vyhledá nadřazenou složku pro soubor řešení, který má stejný název souboru projektu. Například příkaz `devenv /build myproject1.vbproj` vyhledá nadřazená složka pro soubor řešení s názvem "myproject1.sln".

    > [!NOTE]
    > Pouze jeden soubor řešení, která odkazuje na Tenhle projekt se musí nacházet ve své nadřazené složky. Pokud nadřazené složky neobsahuje žádný soubor řešení, odkazuje na Tenhle projekt, nebo pokud nadřazená složka obsahuje dvě nebo více souborů řešení, které na ni odkazují, řešení dočasný soubor vytvořen.

- Cesty k souborům a názvy souborů obsahují mezery, je nutné je uzavřít do uvozovek (""). Například "c:\project\\".

- Vložte jeden znak mezery mezi přepínače a argumenty na stejném řádku. Například příkaz **devenv/log výstup.txt** otevře IDE a vypíše všechny výstup.txt protokolovat informace pro tuto relaci.

- Nemůžete použít porovnávání syntaxi `devenv` příkazy.

## <a name="devenv-switches"></a>Přepínače nástroje devenv

Následující přepínače příkazového řádku zobrazit rozhraní IDE a popisuje úlohu provést.

|Přepínač příkazového řádku|Popis|
|-------------------------|-----------------|
|[/ Příkaz](../../ide/reference/command-devenv-exe.md)|Spuštění rozhraní IDE a spustí zadaný příkaz.|
|[/ Debugexe –](../../ide/reference/debugexe-devenv-exe.md)|Načte C++ executable pod kontrolou ladicího programu. Tento přepínač není k dispozici pro spustitelné soubory Visual Basic a C#. Další informace najdete v tématu [automaticky spustit proces v ladicím programu](../../debugger/debug-multiple-processes.md#BKMK_Automatically_start_an_process_in_the_debugger).|
|[/ LCID nebo/l](../../ide/reference/lcid-devenv-exe.md)|Nastaví výchozí jazyk pro prostředí IDE. Pokud zadaný jazyk není součástí vaší instalace sady Visual Studio, toto nastavení je ignorováno.|
|[/ Log](../../ide/reference/log-devenv-exe.md)|Spuštění sady Visual Studio a protokoly všechny aktivity v souboru protokolu.|
|[/ Run nebo /r](../../ide/reference/run-devenv-exe.md)|Zkompiluje a spustí zadaného řešení.|
|[/Runexit](../../ide/reference/runexit-devenv-exe.md)|Zkompiluje a spustí zadaného řešení, minimalizuje IDE při řešení spuštění a ukončení IDE po dokončení řešení.|
|[/ UseEnv](../../ide/reference/useenv-devenv-exe.md)|Způsobí, že rozhraní IDE, má-li použít CESTU, zahrnout a LIB proměnné prostředí pro kompilaci C++, namísto nastavení zadané v části adresáře VC ++ **projekty** možnosti v **možnosti** dialogové okno. Tento přepínač. je nainstalovaná se systémem **vývoj aplikací s jazykem C++** zatížení. Další informace najdete v tématu [nastavení cesty a proměnných prostředí pro sestavení příkazového řádku](/cpp/build/setting-the-path-and-environment-variables-for-command-line-builds).|
|[Či upravit](../../ide/reference/edit-devenv-exe.md)|Zadané soubory se otevře v spuštěné instance této aplikace. Pokud nejsou žádné spuštěné instance, spustí novou instanci s rozložení zjednodušené okna.|
|[/ SafeMode](../../ide/reference/safemode-devenv-exe.md)|Visual Studio se spustí v nouzovém režimu a načte výchozí prostředí a služeb a dodává verze balíčků třetích stran.|
|[/ Resetskippkgs –](../../ide/reference/resetskippkgs-devenv-exe.md)|Vymaže všechny SkipLoading značky, které byly přidány do VSPackages uživatelé, kteří chtějí předejít přetížení problém VSPackages.|
|[Nebo instalační program](../../ide/reference/setup-devenv-exe.md)|Vynutí Visual Studio sloučit prostředků metadata, která popisuje nabídek, panely nástrojů a příkaz skupin, ze všech VSPackages k dispozici. Tento příkaz musí spustit jako správce.|

Následující přepínače příkazového řádku nezobrazují rozhraní IDE.

|Přepínač příkazového řádku|Popis|
|-------------------------|-----------------|
|[/?](../../ide/reference/q-devenv-exe.md)|Zobrazí nápovědu pro devenv přepínače v **okno příkazového řádku**.<br /><br /> **Devenv /?**|
|[/ Sestavení](../../ide/reference/build-devenv-exe.md)|Vytvoří zadaného řešení nebo projektu závislosti na konfiguraci zadaného řešení.<br /><br /> **/ Build myproj.csproj nástroje devenv**|
|[/ Clean](../../ide/reference/clean-devenv-exe.md)|Odstraní všechny soubory vytvořené sestavení příkazu, aniž by to ovlivnilo zdrojové soubory.<br /><br /> **DEVENV myproj.csproj / clean**|
|[/ Nasazení](../../ide/reference/deploy-devenv-exe.md)|Sestavení řešení, společně s soubory potřebné pro nasazení, podle konfigurace řešení.<br /><br /> **DEVENV myproj.csproj / nasazení**|
|[/ Rozdílů](../../ide/reference/diff.md)|Porovná dva soubory. Používá čtyři parametry: zdrojový soubor, TargetFile, SourceDisplayName (volitelné), TargetDisplayName (volitelné).|
|[/ Out](../../ide/reference/out-devenv-exe.md)|Umožňuje zadat soubor, který chcete docházet k chybám při sestavování.<br /><br /> **/ Build myproj.csproj DEVENV vstupně -výstupnímu log.txt**|
|[/Project](../../ide/reference/project-devenv-exe.md)|Projekt sestavení, vyčistit nebo nasadit. Tento přepínač lze použít pouze v případě, že jste zadali také/Build, / rebuild / vyčistit, nebo / deploy – přepínač.|
|[/ProjectConfig](../../ide/reference/projectconfig-devenv-exe.md)|Určuje projekt konfiguraci sestavení nebo nasadit. Tento přepínač lze použít pouze v případě, že jste zadali také přepínač/Project.|
|[/ Rebuild](../../ide/reference/rebuild-devenv-exe.md)|Vyčistí a potom vytvoří zadaného řešení nebo projektu závislosti na konfiguraci zadaného řešení.|
|[/ Resetsettings –](../../ide/reference/resetsettings-devenv-exe.md)|Obnoví výchozí nastavení sady Visual Studio. Volitelně obnoví nastavení .vssettings zadaný soubor.|
|[/ Upgrade](../../ide/reference/upgrade-devenv-exe.md)|Upgraduje aktuální formátech Visual Studio pro tyto soubory soubor zadaný řešení a všechny jeho soubory projektu nebo soubor zadaný projekt.|

## <a name="see-also"></a>Viz také

* [Obecné, prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)