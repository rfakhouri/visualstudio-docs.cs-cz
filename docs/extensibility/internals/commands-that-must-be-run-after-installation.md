---
title: "Příkazy, které se musí spustit po instalaci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- post-install commands
ms.assetid: c9601f2e-2c6e-4da9-9a6e-e707319b39e2
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2ff4b1e572fd1e0c5c500fbd756d01063665bd1f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="commands-that-must-be-run-after-installation"></a>Příkazy, které se musí spustit po instalaci
Pokud nasazujete rozšíření prostřednictvím soubor MSI, je nutné spustit `devenv /setup` jako součást instalace v pořadí pro sadu Visual Studio pro zjišťování rozšíření.  
  
> [!NOTE]
>  Informace v tomto tématu se vztahují na hledání DevEnv s Visual Studio 2008 a starší. Informace o tom, jak zjišťovat DevEnv s novější verzí sady Visual Studio najdete v tématu [zjišťování požadavky na systém](../../extensibility/internals/detecting-system-requirements.md).  
  
## <a name="finding-devenvexe"></a>Hledání devenv.exe  
 Můžete vyhledat jednotlivých verzí devenv.exe z registru hodnoty, které [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] zápisu instalační programy pomocí RegLocator tabulka a tabulka AppSearch ukládání hodnoty registru jako vlastnosti. Další informace najdete v tématu [zjišťování požadavky na systém](../../extensibility/internals/detecting-system-requirements.md).  
  
### <a name="reglocator-table-rows-to-locate-devenvexe-from-different-versions-of-visual-studio"></a>Řádky tabulky RegLocator najít devenv.exe z různých verzí sady Visual Studio  
  
|Signature_|kořenové|Key|Název|Typ|  
|-----------------|----------|---------|----------|----------|  
|RL_DevenvExe_2002|2|SOFTWARE\Microsoft\VisualStudio\7.0\Setup\VS|EnvironmentPath|2|  
|RL_DevenvExe_2003|2|SOFTWARE\Microsoft\VisualStudio\7.1\Setup\VS|EnvironmentPath|2|  
|RL_DevenvExe_2005|2|SOFTWARE\Microsoft\VisualStudio\8.0\Setup\VS|EnvironmentPath|2|  
|RL_DevenvExe_2008|2|SOFTWARE\Microsoft\VisualStudio\9.0\Setup\VS|EnvironmentPath|2|  
  
### <a name="appsearch-table-rows-for-corresponding-reglocator-table-rows"></a>Řádky tabulky AppSearch odpovídající RegLocator řádků tabulky  
  
|Vlastnost|Signature_|  
|--------------|-----------------|  
|DEVENV_EXE_2002|RL_DevenvExe_2002|  
|DEVENV_EXE_2003|RL_DevenvExe_2003|  
|DEVENV_EXE_2005|RL_DevenvExe_2005|  
|DEVENV_EXE_2008|RL_DevenvExe_2008|  
  
 Například instalační program sady Visual Studio zapíše hodnotu registru **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\9.0\Setup\VS\EnvironmentPath** jako **C:\VS2008\Common7\IDE\devenv.exe**, kompletní cesta ke spustitelnému souboru, musíte spustit instalační program.  
  
 **Poznámka:** ho, protože sloupec typu RegLocator 2, není potřeba zadat další informace o verzi v tabulce podpis.  
  
## <a name="running-devenvexe"></a>Spuštění devenv.exe  
 Každou vlastnost v tabulce AppSearch po AppSearch standardní akce spustí v instalačním programu, má hodnotu odkazující na soubor devenv.exe pro odpovídající verzi sady Visual Studio. Některé z hodnot registru, pokud nejsou zadány – vzhledem k tomu, že tato verze sady Visual Studio není nainstalována – zadanou vlastnost nastavena na hodnotu null.  
  
 Instalační služba systému Windows podporuje spuštění na kterou odkazuje vlastnost spustitelný soubor pomocí vlastní akce zadejte 50. Vlastní akce by měla obsahovat možnosti spuštění ve skriptu, msidbCustomActionTypeInScript (1024) a msidbCustomActionTypeCommit (512) k zajištění, že VSPackage byla úspěšně nainstalována před integrace do [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Další informace najdete v tématu CustomAction tabulky a možnosti spuštění vlastní akce ve skriptu.  
  
 Vlastní akce typu 50 určovat vlastnost obsahující spustitelného souboru jako hodnotu zdrojový sloupec a argumenty příkazového řádku v cílový sloupec.  
  
### <a name="customaction-table-rows-to-run-devenvexe"></a>Řádky tabulky CustomAction ke spuštění devenv.exe  
  
|Akce|Typ|Zdroj|cíl|  
|------------|----------|------------|------------|  
|CA_RunDevenv2002|1586|DEVENV_EXE_2002|/ Setup|  
|CA_RunDevenv2003|1586|DEVENV_EXE_2003|/ Setup|  
|CA_RunDevenv2005|1586|DEVENV_EXE_2005|/ Setup|  
|CA_RunDevenv2008|1586|DEVENV_EXE_2008|/ Setup|  
  
 Vlastní akce musí být vytvořené do tabulky InstallExecuteSequence k jejich plánování pro spuštění během instalace. Použijte k odpovídající vlastnost v každém řádku sloupce podmínky brání provedení vlastní akce se spustit, pokud tuto verzi [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] není nainstalovaná v systému.  
  
> [!NOTE]
>  `Null`vyhodnocení vlastnosti `False` při použití v podmínkách.  
  
 Hodnota pořadí sloupce pro každý vlastní akce závisí na jiné hodnoty sekvence na balíček Instalační služby systému Windows. Pořadí hodnoty by měly být tak, aby vlastní akce devenv.exe spustit jako nejblíže bezprostředně před parametr InstallFinalize standardní akce.  
  
### <a name="installexecutesequence-table-to-schedule-the-devenvexe-custom-actions"></a>Tabulka InstallExecuteSequence při plánování devenv.exe vlastní akce  
  
|Akce|Podmínka|Pořadí|  
|------------|---------------|--------------|  
|CA_RunDevenv2002|DEVENV_EXE_2002|6602|  
|CA_RunDevenv2003|DEVENV_EXE_2003|6603|  
|CA_RunDevenv2005|DEVENV_EXE_2005|6605|  
|CA_RunDevenv2008|DEVENV_EXE_2008|6608|  
  
## <a name="see-also"></a>Viz také  
 [Instalace balíčků VSPackage pomocí Instalační služby systému Windows](../../extensibility/internals/installing-vspackages-with-windows-installer.md)