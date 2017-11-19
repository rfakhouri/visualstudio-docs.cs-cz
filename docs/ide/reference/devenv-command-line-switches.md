---
title: "Příkazového řádku DEVENV | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- switches, Devenv
- builds [Team System], command-line
- applications [Visual Studio], executing
- compiling source code, Devenv
- command-line switches, Devenv
- command line [Visual Studio], switches
- Devenv
- environment, Devenv commands
- compilers, Devenv commands
- switches
- Devenv, syntax and list of switches
ms.assetid: e12bc6ed-74fd-4bea-8d7c-89b99c20bad8
caps.latest.revision: "33"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a22ac991b88dd62c91a9bf08f5397fe80e4ae37d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="devenv-command-line-switches"></a>Devenv – přepínače příkazového řádku
DEVENV umožňuje nastavit různé možnosti pro integrované vývojové prostředí (IDE) a také vytvářet, ladit a nasazení projektů z příkazového řádku. Pomocí přepínače pro spuštění prostředí IDE ze skriptu nebo soubor .bat, například skript noční sestavení, nebo spuštění rozhraní IDE v konkrétní konfigurací.  
  
> [!NOTE]
>  O úlohách spojených s sestavení teď doporučujeme použít nástroj MSBuild místo nástroje devenv. Další informace najdete v tématu [Reference k příkazovému řádku](../../msbuild/msbuild-command-line-reference.md).  
  
> [!NOTE]
>  Devenv musíte spustit jako správce Chcete-li použít [/Setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) a [/installvstemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) přepínače.  
  
## <a name="devenv-switch-syntax"></a>Syntaxe – přepínač nástroje devenv  
 Ve výchozím nastavení příkazy nástroje devenv předat nástroj devenv.com přepínače.  
  
 Nástroj devenv.com poskytuje pro doručení výstupu prostřednictvím datových proudů standardní systému, například `stdout` a `stderr`a určí příslušné přesměrování vstupů/výstupů v případě zachycení výstup, například do souboru TXT. Příkazy, které začínají místo `devenv.exe` můžete použít stejné přepínače, ale bude posílat do programu devenv.exe obcházení nástroj devenv.com.  
  
 Syntaxe pravidla pro `devenv` přepínače vypadat podobně jako u jiných DOS nástroje příkazového řádku. Platí pro všechny následující syntaxe pravidla `devenv` přepínače a jejich argumenty:  
  
-   Příkazy začínat `devenv`.  
  
-   Přepínače nerozlišují malá a velká písmena.  
  
-   Při zadávání řešení nebo projektu, je prvním argumentem Název řešení soubor nebo soubor projektu, včetně cesta k souboru.  
  
-   Pokud první argument je soubor, který není projekt nebo řešení, bude tento soubor otevřete v editoru odpovídající v nové instanci rozhraní IDE.  
  
-   Pokud zadáte název souboru projektu místo názvu souboru řešení `devenv` příkaz Hledat nadřazenou složku pro soubor řešení, který má stejný název souboru projektu. Například příkaz `devenv /build myproject1.vbproj` hledat nadřazená složka pro soubor řešení s názvem "myproject1.sln".  
  
    > [!NOTE]
    >  Pouze jeden soubor řešení, která odkazuje na Tenhle projekt se musí nacházet ve své nadřazené složky. Pokud nadřazená složka obsahuje soubor žádné řešení, která odkazuje na Tenhle projekt, nebo pokud nadřazená složka obsahuje dvě nebo více souborů řešení, které na ni odkazují, pak do dočasného souboru řešení bude vytvořen, název pro tento projekt a na ni odkazuje.  
  
-   Cesty k souborům a názvy souborů obsahují mezery, je nutné je uzavřít do uvozovek (""). Například "c:\project\\".  
  
-   Vložte jeden znak mezery mezi přepínače a argumenty na stejném řádku. Například příkaz **devenv/log výstup.txt** otevře IDE a vypíše všechny výstup.txt protokolovat informace pro tuto relaci.  
  
-   Nemůžete použít porovnávání syntaxi `devenv` příkazy.  
  
## <a name="devenv-switches"></a>Přepínače nástroje devenv  
 Použijte následující přepínače příkazového řádku zobrazíte IDE a provedení popsané úlohy.  
  
|Přepínač příkazového řádku|Popis|  
|-------------------------|-----------------|  
|[/ Příkazu (devenv.exe)](../../ide/reference/command-devenv-exe.md)|Spuštění rozhraní IDE a spustí zadaný příkaz.|  
|[/ Debugexe – (devenv.exe)](../../ide/reference/debugexe-devenv-exe.md)|Načítání [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] spustitelného souboru pod kontrolou ladicího programu. Tento přepínač není k dispozici pro [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] nebo [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] spustitelné soubory. Další informace najdete v tématu [automaticky spustit proces v ladicím programu](../../debugger/debug-multiple-processes.md#BKMK_Automatically_start_an_process_in_the_debugger).|  
|[/ LCID (devenv.exe)](../../ide/reference/lcid-devenv-exe.md) nebo`/l`|Nastaví výchozí jazyk pro prostředí IDE. Pokud zadaný jazyk není součástí vaší instalace sady Visual Studio, bude toto nastavení ignoruje.|  
|[/ Log (devenv.exe)](../../ide/reference/log-devenv-exe.md)|Spustí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a protokoluje všechny aktivity v souboru protokolu.|  
|[Nebo spusťte (devenv.exe)](../../ide/reference/run-devenv-exe.md) nebo`/r`|Zkompiluje a spustí zadaného řešení.|  
|[/ Runexit (devenv.exe)](../../ide/reference/runexit-devenv-exe.md)|Zkompiluje a spustí zadaného řešení, minimalizuje IDE při řešení spuštění a ukončení IDE po dokončení řešení.|  
|[/ UseEnv (devenv.exe)](../../ide/reference/useenv-devenv-exe.md)|Způsobí, že rozhraní IDE, má-li použít CESTU, zahrnout a LIB proměnných prostředí pro [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] kompilace místo nastavení zadané v části adresáře VC ++ **projekty** možnosti v **možnosti** Dialogové okno. Další informace najdete v tématu [nastavení cesty a proměnných prostředí pro sestavení příkazového řádku](/cpp/build/setting-the-path-and-environment-variables-for-command-line-builds)|  
|[Či upravit (devenv.exe)](../../ide/reference/edit-devenv-exe.md)|Zadané soubory se otevře v spuštěné instance této aplikace. Pokud nejsou žádné spuštěné instance, spustí novou instanci rozložení zjednodušené okna.|  
|[/ ResetAddin (devenv.exe)](../../ide/reference/resetaddin-devenv-exe.md)|Spustí instanci Visual Studio IDE bez načtení zadaného Add-in.|  
|[/ SafeMode (devenv.exe)](../../ide/reference/safemode-devenv-exe.md)|Spustí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] v nouzovém režimu a načte výchozí prostředí a služeb a dodaný verzích balíčky jiných výrobců.|  
|[/ Resetskippkgs – (devenv.exe)](../../ide/reference/resetskippkgs-devenv-exe.md)|Vymaže všechny SkipLoading značky, které byly přidány do VSPackages uživatelé, kteří chtějí předejít přetížení problém VSPackages.|  
|[Nebo instalační program (devenv.exe)](../../ide/reference/setup-devenv-exe.md)|Vynutí Visual Studio sloučit prostředků metadata, která popisuje nabídek, panely nástrojů a příkaz skupin, ze všech VSPackages k dispozici.|  
  
 K provedení popsané úlohy použijte následující přepínače příkazového řádku. Tyto přepínače příkazového řádku nezobrazují rozhraní IDE.  
  
|Přepínač příkazového řádku|Popis|  
|-------------------------|-----------------|  
|[/? (devenv.exe)](../../ide/reference/q-devenv-exe.md)|Zobrazí nápovědu pro devenv přepínače v **okno příkazového řádku**.<br /><br /> **Devenv /?**|  
|[/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)|Vytvoří zadaného řešení nebo projektu závislosti na konfiguraci zadaného řešení.<br /><br /> **/ Build myproj.csproj nástroje devenv**|  
|[/ Clean (devenv.exe)](../../ide/reference/clean-devenv-exe.md)|Odstraní všechny soubory vytvořené sestavení příkazu, aniž by to ovlivnilo zdrojové soubory.<br /><br /> **DEVENV myproj.csproj / clean**|  
|[/ Nasadit (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)|Sestavení řešení, společně s soubory potřebné pro nasazení, podle konfigurace řešení.<br /><br /> **DEVENV myproj.csproj / nasazení**|  
|[/ Rozdílů](../../ide/reference/diff.md)|Porovná dva soubory.  Má čtyři parametry: zdrojový soubor, TargetFile, SourceDisplayName(optional),TargetDisplayName(optional).|  
|[/ InstallVSTemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md)|Zaregistruje projekt nebo položku šablony, které se nacházejí v  *\<VisualStudioInstallDir >*\Common7\IDE\ProjectTemplates nebo  *\<VisualStudioInstallDir >*\Common7 \IDE\ItemTemplates tak, že jsou dostupné prostřednictvím **nový projekt** a **přidat novou položku** dialogová okna.<br /><br /> **/ Installvstemplates nástroje devenv**|  
|[/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)|Umožňuje zadat soubor, který chcete docházet k chybám při sestavování.<br /><br /> **/ Build myproj.csproj DEVENV vstupně -výstupnímu log.txt**|  
|[/ Project (devenv.exe)](../../ide/reference/project-devenv-exe.md)|Projekt sestavení, vyčistit nebo nasadit. Tento přepínač lze použít pouze v případě, že jste zadali také/Build, / rebuild / vyčistit, nebo / deploy – přepínač.|  
|[/ ProjectConfig (devenv.exe)](../../ide/reference/projectconfig-devenv-exe.md)|Určuje projekt konfiguraci sestavení nebo nasadit. Tento přepínač lze použít pouze v případě, že jste zadali také přepínač/Project.|  
|[/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)|Vyčistí a potom vytvoří zadaného řešení nebo projektu závislosti na konfiguraci zadaného řešení.|  
|[/ Resetsettings – (devenv.exe)](../../ide/reference/resetsettings-devenv-exe.md)|Obnoví výchozí nastavení sady Visual Studio. Volitelně obnoví nastavení .vssettings zadaný soubor.|  
|[/ Updateconfiguration (devenv.exe)](../../ide/reference/updateconfiguration-devenv-exe.md)|Upozorní [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sloučit [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] balíčků na systém a kontroly MEF mezipaměti pro všechny změny.|  
|[Nebo upgradovat (devenv.exe)](../../ide/reference/upgrade-devenv-exe.md)|Upgraduje soubor zadaný řešení a všechny jeho soubory projektu nebo soubor zadaný projekt na aktuální [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] formátech pro tyto soubory.|  
  
## <a name="see-also"></a>Viz také  
 [Obecné, prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)