---
title: "Profilace v prostředí HPC (High Performance Computing) clusterů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.performance.hpc.wizard.exeoptions
- vs.performance.hpc.wizard.summary
- vs.performance.hpc.wizard.startoptions
- vs.performance.hpc.wizard.intro
- vs.performance.hpc.property.basic
- vs.performance.hpc.wizard.application
- vs.performance.hpc.wizard.clusteroptions
- vs.performance.hpc.property.advanced
helpviewer_keywords:
- profililng tools,HPC
- HPC profiling
ms.assetid: 1525bbdb-27da-4088-8487-a486cee5e7b3
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 53fea09175d9d9653dd4552832cd511ed7900b8e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="profiling-on-hpc-high-performance-computing-clusters"></a>Profilace v klastrech HPC (High Performance Computing)
Můžete profilu na výpočetní uzly clusterů Microsoft Windows HPC pomocí metody vzorkování [!INCLUDE[vsPreExt](../profiling/includes/vspreext_md.md)] nebo [!INCLUDE[vsUltExt](../profiling/includes/vsultext_md.md)] nástrojích pro profilaci. Další informace o prostředí HPC naleznete v části [Windows HPC](http://go.microsoft.com/fwlink/?LinkId=165393) na webu společnosti Microsoft.  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li profil na výpočetním uzlu HPC, musíte udělat následující:  
  
-   Nainstalujte Microsoft HPC Pack 2008 na stejném počítači jako [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)]. Počítač nemá být součástí clusteru prostředí HPC. HPC Pack na můžete nainstalovat [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=177414).  
  
-   Nainstalujte [!INCLUDE[net_v40_long](../code-quality/includes/net_v40_long_md.md)] a samostatné verze nástroje pro profilaci na HPC výpočetního uzlu. Nainstalovat programy pro oba [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] a jsou dostupné na samostatný profiler [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] instalačního média. **Poznámka:** po instalaci je třeba restartovat výpočetní [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] a před instalací nástrojů pro profilaci.  
  
 K instalaci [!INCLUDE[net_v40_long](../code-quality/includes/net_v40_long_md.md)] a samostatné profilace nástroje na aktivní HPC výpočetního uzlu a povolte profilace na počítači clusteru, postupujte takto:  
  
1.  Otevřete okno příkazového řádku, který je nainstalován pomocí sady HPC pack.  
  
2.  Samostatné příkazového řádku zadejte následující příkazy:  
  
    1.  `clusrun /all /scheduler:`*% HeadNode % FxPath %*`/q /norestart`  
  
    2.  `clusrun /all /scheduler:`*HeadNode %*`shutdown /r /t 0 /d u:4:2 /c "Microsoft .NET Framework install required restart"`  
  
    3.  `clusrun /all /scheduler:`*% HeadNode % ProfilerPath %*`/q /norestart`  
  
|||  
|-|-|  
|*% HeadNode %*|Název hlavního uzlu clusteru.|  
|*% FxPath %*|Cesta ke [!INCLUDE[net_v40_long](../code-quality/includes/net_v40_long_md.md)] Instalační služby. Na [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] instalačním médiu je cesta: WCU\dotNetFramework\dotNetFx40_Full_x86_x64.exe|  
|*% ProfilerPath %*|Cesta k samostatnou verzi nástrojích pro profilaci Instalační služby. Na [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] instalačním médiu je cesta: samostatné Profiler\x64\vs_profiler.exe|  
  
## <a name="profiling-on-an-hpc-compute-node"></a>Profilace do výpočetního uzlu HPC  
 Relace profilování nakonfigurujete pomocí Průvodce výkonu HPC k zadání informací HPC, clusteru a cíle. Na stránkách vlastností relace výkonu můžete nastavit další možnosti. Nástroje pro profilaci automaticky nasadit binární soubory nutné cíl a spusťte profileru a aplikace prostředí HPC.  
  
#### <a name="to-profile-on-an-hpc-compute-node"></a>Do profilu do výpočetního uzlu HPC  
  
1.  Na **analyzovat** nabídky, klikněte na tlačítko **spusťte Průvodce výkonu HPC**. Pokud příkaz není k dispozici, ujistěte se, že splňujete požadavky uvedené výše.  
  
2.  Klikněte na tlačítko **Další** na první stránce průvodce.  
  
3.  Na druhé stránce průvodce vyberte aplikaci, kterou chcete profil.  
  
    -   Projekt, který je aktuálně otevřený v profilu [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], vyberte **jeden nebo více dostupných projektů** možnost a potom vyberte název projektu ze seznamu.  
  
    -   Binární soubor, který není součástí profilu otevřeného projektu vyberte **spustitelný soubor (. Soubor EXE)** možnost.  
  
4.  Klikněte na tlačítko **Další**.  
  
5.  Na třetí stránce průvodce:  
  
    -   Pokud jsou profilace spustitelné soubory, které není v otevřeném projektu, zadejte cestu k binárnímu souboru v **co je úplná cesta ke spustitelnému souboru**.  
  
    -   Pokud jsou profilace spustitelné soubory, které není v otevřeném projektu, můžete zadat žádných argumentů příkazového řádku mají být předána do procesu **argumenty příkazového řádku**.  
  
    -   V **vzdálené pracovní adresář**, zadejte cestu ke složce, který je používán instancí procesu na jednotlivých výpočetních uzlů.  
  
    -   V **umístění nasazení**, zadejte cestu k adresáři, který používá HPC server do fáze bitových kopií pro nasazení.  
  
6.  Klikněte na tlačítko **Další**.  
  
7.  Na čtvrté stránce průvodce:  
  
    -   V **hlavní uzel** seznamu, klikněte na počítač, který funguje jako hlavního uzlu HPC v profilaci spustit. Hlavní uzel může být "localhost", což vám umožní profilu v místním počítači bez nutnosti pro cluster s podporou.  
  
    -   V **počet procesů** klikněte na počet instancí aplikace ke spuštění.  
  
    -   Z **profilace možnosti** seznamu, vyberte cíl profilování.  
  
         Chcete-li profil specifickém procesu v clusteru, vyberte **profilu v pořadí** možnost a potom vyberte pořadí procesu z rozevíracího seznamu.  
  
         Profilu proces nebo procesy, které běží na konkrétním uzlu v clusteru HPC, vyberte **profilu v uzlu** možnost a pak vyberte uzel z rozevíracího seznamu.  
  
8.  Klikněte na tlačítko **Další**.  
  
9. Na stránce páté průvodce můžete k okamžitému spuštění profileru a proces profilování nebo ke spuštění profilování později pomocí Průzkumníka výkonu.  
  
    -   Vyberte **spuštění profilace po ukončení průvodce** ke spuštění profilace okamžitě, nebo zrušte zaškrtnutí políčka ke spuštění profilování ručně.  
  
10. Klikněte na tlačítko **Dokončit**.  
  
## <a name="setting-hpc-profiling-properties-by-using-performance-session-property-pages"></a>Nastavení vlastností HPC profilace pomocí stránky vlastností relace výkonu  
 Můžete změnit vlastnosti výkonnostní relace, která jste nastavili v prostředí HPC profilace průvodci na stránce Vlastnosti spusťte HPC stránky vlastností relace výkonu. Můžete nastavit další možnosti na stránce HPC rozšířené vlastnosti.  
  
#### <a name="to-open-the-performance-session-property-pages"></a>K otevření stránek vlastností relace výkonu  
  
1.  V případě potřeby otevřete soubor relace (.psess) výkonu v Průzkumníku výkonu. Na **soubor** nabídky, klikněte na tlačítko **otevřete** a vyhledejte soubor.  
  
2.  Prohlížeč výkonu, klikněte pravým tlačítkem na název relace výkonu a pak klikněte na **vlastnosti**.  
  
3.  V dialogovém okně vlastností stránky použijte jednu z následujících metod:  
  
    -   Klikněte na tlačítko **Obecné** a pak vyberte **shromažďovat v clusteru HPC** Chcete-li HPC profilace na nebo zrušte zaškrtnutí políčka Zakázat HPC profilace.  
  
    -   Klikněte na tlačítko **HPC spusťte vlastnosti** ke změně vlastností, které začínají aplikace prostředí HPC.  
  
    -   Klikněte na tlačítko **HPC Upřesnit vlastnosti** můžete nastavit další možnosti  
  
### <a name="hpc-launch-properties"></a>Vlastnosti spuštění HPC  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|**Hlavní uzel**|Určuje počítače, který funguje jako hlavního uzlu HPC v profilaci spustit.|  
|**Počet procesů**|Určuje počet instancí aplikace ke spuštění v PROFILOVANÉHO aplikaci.|  
|**Profil v pořadí**|Chcete-li profil specifickém procesu v clusteru, vyberte **profilu v pořadí** možnost a potom vyberte pořadí procesu z rozevíracího seznamu.|  
|**Profil v uzlu**|Profilu proces nebo procesy, které běží na konkrétním uzlu v clusteru HPC, vyberte **profilu v uzlu** možnost a pak vyberte uzel z rozevíracího seznamu.|  
|**Vzdálené pracovní adresář**|Určuje cestu ke složce, který je používán instancí procesu na jednotlivých výpočetních uzlů.|  
|**Umístění nasazení**|Určuje cestu k adresáři, který používá HPC server do fáze bitových kopií pro nasazení.|  
  
### <a name="advanced-properties"></a>Upřesnit vlastnosti  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|**Název projektu**|Název aktuální [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] projekt nebo řešení.|  
|**Vyčištění při zastavení profileru**|V případě hodnoty true odebere binárních souborů, které jsou nasazené do adresáře provádění. V tomto kroku se neodeberou souborů a adresářů vytvořené programem uživatele. Pokud provádění a nasazení adresáře byly vytvořeny pomocí rozhraní IDE, rozhraní IDE se pokusí odebrat je ale neprovádí, pokud mají soubory není nasazené pomocí rozhraní IDE.|  
|**Další soubory pro nasazení**|Určuje seznam oddělený středníkem případných dalších souborů k nasazení na výpočetním uzlu. Kliknutí tlačítko se třemi tečkami (**...** ) vyberte několik souborů pomocí dialogového okna.|  
|**Příkaz Mpiexec**|Určuje aplikace, která spustí aplikaci, která MPI. Výchozí hodnota je **mpiexec.exe**|  
|**Argumenty Mpiexec**|Určuje argumenty, které mají být předán příkazu mpiexec.exe.|  
|**Požadovaný uzly v clusteru**|Určuje počet uzlů v clusteru, na který se má spustit aplikace.|  
|**Nasazení souborů CRT**|V případě hodnoty true nasadí C/C++, doba spuštění v clusteru.|  
|**Předem profilu skriptu**|Určuje název a cesta k souboru skriptu ke spuštění na místním vývojovém počítači před zahájením relace profilování.|  
|**Předem profilu argumenty skriptu**|Určuje argumenty, které mají předat do skriptu před profilu.|  
|**Skript po profilu**|Určuje název a cesta k souboru skriptu ke spuštění na místním vývojovém počítači po ukončení relace profilování.|  
|**Argumenty skriptu po profilu**|Určuje argumenty, které mají předat do skriptu po profilu.|