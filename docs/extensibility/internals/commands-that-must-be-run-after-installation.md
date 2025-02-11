---
title: Příkazy, které musí spustit po instalaci | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- post-install commands
ms.assetid: c9601f2e-2c6e-4da9-9a6e-e707319b39e2
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d8a59e1a6613936c586c5529dcfc6a56a957112c
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66341995"
---
# <a name="commands-that-must-be-run-after-installation"></a>Příkazy, které musí spustit po instalaci
Pokud nasazení vašeho rozšíření prostřednictvím *MSI* souboru, je nutné spustit **devenv/Setup** jako součást vaší instalaci sady Visual Studio ke zjištění vašich rozšíření.

> [!NOTE]
> Informace v tomto tématu se vztahují na hledání *devenv.exe* za použití Visual Studio 2008 a starší. Informace o tom, jak zjišťovat *devenv.exe* s novější verzí sady Visual Studio, přečtěte si téma [zjistit požadavky na systém](../../extensibility/internals/detecting-system-requirements.md).

## <a name="find-devenvexe"></a>Najít devenv.exe
 Můžete najít všechny verze *devenv.exe* z registru hodnot, které [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] instalační programy zápisu, pomocí RegLocator tabulky a AppSearch tabulek pro ukládání hodnot registru jako vlastnosti. Další informace najdete v tématu [zjistit požadavky na systém](../../extensibility/internals/detecting-system-requirements.md).

### <a name="reglocator-table-rows-to-locate-devenvexe-from-different-versions-of-visual-studio"></a>Řádky tabulky RegLocator najít devenv.exe z různých verzí sady Visual Studio

|podpis|Kořenové|Key|Name|Type|
|-----------------|----------|---------|----------|----------|
|RL_DevenvExe_2002|2|SOFTWARE\Microsoft\VisualStudio\7.0\Setup\VS|EnvironmentPath|2|
|RL_DevenvExe_2003|2|SOFTWARE\Microsoft\VisualStudio\7.1\Setup\VS|EnvironmentPath|2|
|RL_DevenvExe_2005|2|SOFTWARE\Microsoft\VisualStudio\8.0\Setup\VS|EnvironmentPath|2|
|RL_DevenvExe_2008|2|SOFTWARE\Microsoft\VisualStudio\9.0\Setup\VS|EnvironmentPath|2|

### <a name="appsearch-table-rows-for-corresponding-reglocator-table-rows"></a>Řádky tabulky AppSearch odpovídající RegLocator řádků tabulky

|Vlastnost|podpis|
|--------------|-----------------|
|DEVENV_EXE_2002|RL_DevenvExe_2002|
|DEVENV_EXE_2003|RL_DevenvExe_2003|
|DEVENV_EXE_2005|RL_DevenvExe_2005|
|DEVENV_EXE_2008|RL_DevenvExe_2008|

 Například instalačního programu sady Visual Studio zapíše hodnotu registru **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0\Setup\VS\EnvironmentPath** jako *C:\VS2008\Common7\IDE\devenv.exe*, úplnou cestu ke spustitelnému souboru, musíte spustit instalační program.

> [!NOTE]
> Protože typ sloupce tabulky RegLocator je 2, není nutné zadat další informace o verzi v tabulce podpis.

## <a name="run-devenvexe"></a>Spuštěním devenv.exe
 Každou vlastnost v tabulce AppSearch i po AppSearch standardních akcí spuštění v instalačním programu, obsahuje hodnotu přejdete *devenv.exe* soubor pro odpovídající verzi sady Visual Studio. Jakoukoliv hodnotu registru, pokud nejsou k dispozici, protože není nainstalována verze sady Visual Studio – zadaná vlastnost je nastavena na hodnotu null.

 Spuštění spustitelného souboru, na kterou odkazuje vlastnost prostřednictvím vlastní akci podporuje instalační služby systému Windows zadejte 50. Vlastní akce by měla zahrnovat možnosti spuštění ve skriptu, `msidbCustomActionTypeInScript` (1024) a `msidbCustomActionTypeCommit` (512) k zajištění, že sady VSPackage byla úspěšně nainstalována před integrací do [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Další informace najdete v tématu [CustomAction tabulky](https://docs.microsoft.com/windows/desktop/msi/customaction-table) a [možnosti spuštění ve skriptu vlastní akce](https://docs.microsoft.com/windows/desktop/msi/custom-action-in-script-execution-options).

 Vlastní akce typu 50 určovat vlastnost obsahující spustitelný soubor jako hodnotu zdrojový sloupec a argumenty příkazového řádku v cílový sloupec.

### <a name="customaction-table-rows-to-run-devenvexe"></a>Řádky tabulky CustomAction ke spuštění devenv.exe

|Akce|Type|Source|Target|
|------------|----------|------------|------------|
|CA_RunDevenv2002|1586|DEVENV_EXE_2002|/setup|
|CA_RunDevenv2003|1586|DEVENV_EXE_2003|/setup|
|CA_RunDevenv2005|1586|DEVENV_EXE_2005|/setup|
|CA_RunDevenv2008|1586|DEVENV_EXE_2008|/setup|

 Vlastní akce musí být vytvořen do tabulky InstallExecuteSequence naplánovat pro provedení během instalace. Použijte odpovídající vlastnost v jednotlivých řádcích sloupce podmínka zabráníte tak případnému vlastní akci spuštění jestli verzi [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] není nainstalovaná v systému.

> [!NOTE]
> Vlastnosti s hodnotou Null vyhodnotit `False` při použití v podmínkách.

 Hodnota pořadí sloupce pro všechny vlastní akce závisí na jiné pořadí hodnoty v balíčku Instalační služby systému Windows. Měly by být hodnoty pořadí tak, aby *devenv.exe* vlastní akce Spustit jako nejblíže bezprostředně před parametr InstallFinalize standardních akcí.

### <a name="installexecutesequence-table-to-schedule-the-devenvexe-custom-actions"></a>Tabulka InstallExecuteSequence naplánování devenv.exe vlastní akce

|Akce|Podmínka|Sequence|
|------------|---------------|--------------|
|CA_RunDevenv2002|DEVENV_EXE_2002|6602|
|CA_RunDevenv2003|DEVENV_EXE_2003|6603|
|CA_RunDevenv2005|DEVENV_EXE_2005|6605|
|CA_RunDevenv2008|DEVENV_EXE_2008|6608|

## <a name="see-also"></a>Viz také:
- [Instalace balíčků VSPackage pomocí Instalační služby systému Windows](../../extensibility/internals/installing-vspackages-with-windows-installer.md)