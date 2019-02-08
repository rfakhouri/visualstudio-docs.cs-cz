---
title: Přepínače příkazového řádku nástroje devenv
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- switches, Devenv
- command-line switches, Devenv
- command line [Visual Studio], switches
- Devenv
ms.assetid: e12bc6ed-74fd-4bea-8d7c-89b99c20bad8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a5b7538342cad63d820992fe699e65386f4f3c8e
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55908462"
---
# <a name="devenv-command-line-switches"></a>Přepínače příkazového řádku nástroje devenv

DEVENV umožňuje nastavit různé možnosti pro rozhraní IDE, sestavení projektů, ladění projektů a nasazovat projekty z příkazového řádku. Spuštění rozhraní IDE ze skriptu nebo soubor BAT (například noční sestavení skriptu), nebo spuštění integrovaného vývojového prostředí v konkrétní konfiguraci, použijte tyto přepínače.

> [!NOTE]
> Pro úlohy související s buildem se doporučuje namísto devenv pomocí nástroje MSBuild. Další informace najdete v tématu [odkaz na příkazový řádek MSBuild](../../msbuild/msbuild-command-line-reference.md).

Informace o přepínačích, které se týkají vývoj rozšíření VSPackage, také naleznete v tématu [přepínače příkazového řádku nástroje Devenv pro vývoj rozšíření VSPackage](../../extensibility/devenv-command-line-switches-for-vspackage-development.md).

## <a name="devenv-switch-syntax"></a>Syntaxe přepínač nástroje devenv

Příkazy, které začínají `devenv` jsou zpracovávány `devenv.com` nástroj, který dodává výstup prostřednictvím standardního systému datových proudů, jako například `stdout` a `stderr`. Nástroj určuje příslušné přesměrování vstupů/výstupů v případě, že zaznamenává výstup, třeba do souboru .txt.

Alternativně příkazy, které začínají `devenv.exe` můžete použít stejné přepínače, ale `devenv.com` nástroj přeskočí. Pomocí `devenv.exe` přímo bránil výstup na konzole.

Syntaxe pravidla pro `devenv` přepínače vypadat podobně jako pravidla pro další nástroje pro příkazový řádek DOSU. Následující syntaxe pravidla se vztahují na všechny `devenv` přepínače a jejich argumenty:

- Příkazy začínají `devenv`.

- Přepínače se malá a velká písmena.

- Přepínač můžete zadat použitím spojovníku ("-") nebo lomítka ("/").

- Při zadávání řešení nebo projektu, první argument je název souboru řešení nebo soubor projektu, včetně cesta k souboru.

- Pokud první argument je soubor, který není řešení nebo projektu, tento soubor se otevře ve vhodném editoru v nové instanci integrovaného vývojového prostředí.

- Když zadáte název souboru projektu namísto názvu souboru řešení `devenv` příkaz vyhledá v nadřazené složce souboru projektu, který má stejný název souboru řešení. Například příkaz `devenv myproject1.vbproj /build` vyhledá nadřazené složky pro soubor řešení s názvem `myproject1.sln`.

  > [!NOTE]
  > Jeden a pouze jeden soubor řešení, která odkazuje na tento projekt se musí nacházet v nadřazené složky. Pokud nadřazená složka neobsahuje žádný soubor řešení, která odkazuje na tento projekt, nebo pokud nadřazená složka obsahuje dva nebo více souborů řešení, které na ni odkazují, pak se vytvoří soubor dočasné řešení.

- Když cesty k souborům a názvy souborů obsahují mezery, je nutné je uzavřít do uvozovek (""). Například, `"c:\project a\"`.

- Vložte jeden znak mezery mezi přepínače a argumenty na stejném řádku. Například příkaz `devenv /log output.txt` otevře rozhraní IDE a vypíše všechny výstup.txt zaznamenávat informace o dané relace.

- Nelze použít porovnávání vzorů syntaxe v poznámce `devenv` příkazy.

## <a name="devenv-switches"></a>Přepínače nástroje devenv

Následující přepínače příkazového řádku zobrazí rozhraní IDE a provedení popsané úlohy.

|Přepínač příkazového řádku|Popis|
| - |-----------------|
|[/Command](command-devenv-exe.md)|Spustí rozhraní IDE a provede zadaný příkaz.<br /><br /> `devenv /command "nav https://docs.microsoft.com/"`|
|[/DebugExe](debugexe-devenv-exe.md)|Načte spustitelný C++ pod kontrolu ladicího programu. Tento přepínač není k dispozici v jazyce Visual Basic nebo C# spustitelné soubory. Další informace najdete v tématu [automaticky spustit proces v ladicím programu](../../debugger/debug-multiple-processes.md#BKMK_Automatically_start_an_process_in_the_debugger).<br /><br /> `devenv /debugexe mysln.exe`|
|[/Diff](diff.md)|Porovná dva soubory. Používá čtyři parametry: *Zdrojový soubor*, *Cílovýsoubor*, *SourceDisplayName* (volitelné), a *TargetDisplayName* (volitelné).<br /><br /> `devenv /diff File1 File2 Alias1 Alias2`|
|[/Edit](edit-devenv-exe.md)|Otevře dané soubory v běžící instanci této aplikace. Pokud neexistují žádné spuštěné instance, spustí novou instanci se zjednodušeným rozložením okna.<br /><br /> `devenv /edit File1 File2`|
|[/ LCID nebo/l](lcid-devenv-exe.md)|Nastaví výchozí jazyk, rozhraní IDE. Pokud zadaný jazyk není součástí instalace sady Visual Studio, toto nastavení je ignorováno.<br /><br /> `devenv /l 1033`|
|[/Log](log-devenv-exe.md)|Spuštění sady Visual Studio a zaznamená veškerou aktivitu do souboru protokolu.<br /><br /> `devenv /log mylogfile.xml`|
|[/NoSplash](nosplash-devenv-exe.md)|Otevře rozhraní IDE bez toho, abych úvodní obrazovka.<br /><br /> `devenv /nosplash File1 File2`|
|[/ Run nebo/r](run-devenv-exe.md)|Zkompiluje a spustí zadané řešení.<br /><br /> `devenv /run mysln.sln`|
|[/RunExit](runexit-devenv-exe.md)|Zkompiluje a spustí zadané řešení, minimalizuje integrovaného vývojového prostředí při spuštění řešení a ukončí rozhraní IDE po spuštění řešení.<br /><br /> `devenv /runexit mysln.sln`|
|[/SafeMode](safemode-devenv-exe.md)|Visual Studio spustí v nouzovém režimu. Tento přepínač načte dodané verzi balíčky třetích stran, výchozí služby a výchozí prostředí.<br /><br /> Tento přepínač nepřijímá žádné argumenty.|
|[/UseEnv](useenv-devenv-exe.md)|Způsobí, že integrované vývojové prostředí pro účely CESTU, INCLUDE, LIBPATH a LIB proměnné prostředí kompilace jazyka C++. Tento přepínač je nainstalován se sadou **vývoj desktopových aplikací pomocí C++** pracovního vytížení. Další informace najdete v tématu [nastavení cesty a proměnných prostředí pro sestavení příkazového řádku](/cpp/build/setting-the-path-and-environment-variables-for-command-line-builds).|

Následující přepínače příkazového řádku se nezobrazí integrovaném vývojovém prostředí.

|Přepínač příkazového řádku|Popis|
| - |-----------------|
|[/?](q-devenv-exe.md)|Zobrazí nápovědu pro `devenv` v přepne **okno příkazového řádku**.<br /><br /> Tento přepínač nepřijímá žádné argumenty.|
|[/Build](build-devenv-exe.md)|Sestaví zadané řešení nebo projekt podle konfigurace zadané řešení.<br /><br /> `devenv mysln.sln /build`|
|[/Clean](clean-devenv-exe.md)|Odstraní všechny soubory vytvořené příkazem k sestavení, aniž by to ovlivnilo zdrojové soubory.<br /><br /> `devenv mysln.sln /clean`|
|[/Deploy](deploy-devenv-exe.md)|Sestaví řešení a spolu se soubory, které jsou nezbytné pro nasazení podle konfigurace řešení.<br /><br /> `devenv mysln.sln /deploy`|
|[/Out](out-devenv-exe.md)|Umožňuje zadat soubor, který chcete zobrazovat chyby při sestavování.<br /><br /> `devenv mysln.sln /build Debug /out log.txt`|
|[/Project](project-devenv-exe.md)|Projekt k sestavení, vyčištění nebo nasazení. Tento přepínač můžete použít pouze v případě, že jste jste zadali `/Build`, `/Rebuild`, `/Clean`, nebo `/Deploy` přepnout.<br /><br /> `devenv mysln.sln /build Debug /project proj1`|
|[/ProjectConfig](projectconfig-devenv-exe.md)|Určuje konfiguraci projektu k vytvoření buildu nebo nasazení. Tento přepínač můžete použít pouze v případě, že jste jste zadali `/Project` přepnout.<br /><br /> `devenv mysln.sln /build Release /project proj1 /projectconfig Release`|
|[/Rebuild](rebuild-devenv-exe.md)|Čistí a poté sestaví zadané řešení nebo projekt podle konfigurace zadané řešení.<br /><br /> `devenv mysln.sln /rebuild`|
|[/ResetSettings](resetsettings-devenv-exe.md)|Obnoví výchozí nastavení sady Visual Studio. Volitelně obnoví nastavení zadaného `.vssettings` souboru.<br /><br /> `devenv /resetsettings mysettings.vssettings`|
|[/Upgrade](upgrade-devenv-exe.md)|Upgraduje na aktuální formáty sady Visual Studio pro tyto soubory v zadaném souboru řešení a všechny jeho soubory projektu nebo soubor zadaný projekt.<br /><br /> `devenv mysln.sln /upgrade`|

## <a name="see-also"></a>Viz také:

- [Obecné, Prostředí, dialogové okno Možnosti](general-environment-options-dialog-box.md)
- [Přepínače příkazového řádku nástroje DEVENV pro vývoj rozšíření VSPackage](../../extensibility/devenv-command-line-switches-for-vspackage-development.md)
