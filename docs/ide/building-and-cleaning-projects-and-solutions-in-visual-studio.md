---
title: "Sestavování a čištění projektů a řešení v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.BuildProjectPicker
- vs.batchbuild
helpviewer_keywords:
- Clean Solution command
- builds [Visual Studio], managing
- solution build configurations, starting
- Build Solution command
- project build configurations, starting
- build configurations, starting
- project build configurations, dependencies
- Rebuild Solution command
- solution build configurations, build order
- builds [Visual Studio], preparing
ms.assetid: 710891fd-379e-42c2-a84b-44a7af694ca0
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: faf5978119ef9029db99ae953d5c60876abddabf
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="building-and-cleaning-projects-and-solutions-in-visual-studio"></a>Sestavování a čištění projektů a řešení v sadě Visual Studio
Pomocí postupů v tomto tématu lze vytvořit, znovu sestavit nebo vyčistit všechny nebo některé z projektů nebo položky projektu v řešení. Podrobný kurz, najdete v části [návod: vytváření aplikace](../ide/walkthrough-building-an-application.md).  
  
> [!NOTE]
> Uživatelské rozhraní ve vaší edicí sady Visual Studio může lišit od co toto téma popisuje, v závislosti na nastavení aktivní. Chcete-li změnit nastavení, například k **Obecné** nebo **Visual C++** nastavení, vyberte **nástroje**, **nastavení importu a exportu**a potom Zvolte **obnovit nastavení**.
  
### <a name="to-build-rebuild-or-clean-an-entire-solution"></a>Pokud chcete vytvořit, znovu sestavit nebo vyčištění celé řešení  
  
1.  V **Průzkumníku**, zvolte nebo otevřete řešení.  
  
2.  Na řádku nabídek zvolte **sestavení**a pak vyberte jednu z následujících příkazů:  
  
    -   Zvolte **sestavení** nebo **sestavit řešení** zkompilovat pouze ty soubory a součásti, které se změnily od poslední sestavení projektu.  
  
        > [!NOTE]
        >  **Sestavení** se změní **sestavit řešení** při řešení obsahuje více než jeden projekt.  
  
    -   Zvolte **znovu sestavit řešení** "clean" řešení a následně vytvořit všechny soubory projektu a součásti.  
  
    -   Zvolte **Vyčistit řešení** odstranit všechny zprostředkující a výstupní soubory. Pouze pomocí projektu a součástí souborů vlevo nové instance třídy mezilehlých a výstupní soubory pak se dají vytvářet.  
  
### <a name="to-build-or-rebuild-a-single-project"></a>K sestavení nebo znovu sestavte projekt  
  
1.  V **Průzkumníku**, zvolte nebo otevřete projekt.  
  
2.  Na řádku nabídek zvolte **sestavení**a potom vyberte buď **sestavení***ProjectName* nebo **znovu sestavit***ProjectName*.  
  
    -   Zvolte **sestavení***ProjectName* vytvářet jen ty součásti, které se změnily od poslední sestavení projektu.  
  
    -   Zvolte **znovu sestavit***ProjectName* "vyčistěte" projekt a následně vytvořit soubory projektu a všechny součásti projektu.  
  
### <a name="to-build-only-the-startup-project-and-its-dependencies"></a>K vytvoření spouštěný projekt a jeho závislosti  
  
1.  Na řádku nabídek zvolte **nástroje**, **možnosti**.  
  
2.  V **možnosti** dialogové okno, rozbalte seznam **projekty a řešení** uzel a potom zvolte **sestavit a spustit** stránky.  
  
     **Sestavení a spuštění, projekty a řešení, možnosti** otevře se dialogové okno.  
  
3.  Vyberte **pouze při spuštění sestavení projektů po spuštění a závislosti** zaškrtávací políčko.  
  
     Když toto políčko zaškrtnuto, pouze aktuální projekt po spuštění a jeho závislosti jsou vytvořeny při provádění některé z následujících kroků:  
  
    -   Na řádku nabídek zvolte **ladění**, **spustit** (F5).  
  
    -   Na řádku nabídek zvolte **sestavení**, **sestavit řešení** (CTRL + SHIFT + B).  
  
    Pokud je toto políčko zaškrtnuté, všechny projekty, jejich závislosti a soubory řešení jsou vytvořeny při spuštění některý z předchozích příkazů. Ve výchozím nastavení je toto políčko zaškrtnuté.  
  
### <a name="to-build-only-the-selected-visual-c-project"></a>K vytvoření vybrané projektu Visual C++  
  
1.  Vyberte [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projektu a potom na řádku nabídek zvolte **sestavení**, **projektu pouze**a jeden z následujících příkazů:  
  
    -   **Sestavení pouze** *název projektu*  
  
    -   **Znovu sestavit pouze** *název projektu*  
  
    -   **Čištění pouze** *název projektu*  
  
    -   **Propojit pouze** *název projektu*  
  
    Platí pouze pro tyto příkazy [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projekt, který jste zvolili, bez vytváření, znovu sestavit, čištění nebo propojování žádné závislosti projektu nebo soubory řešení. V závislosti na vaší verzi [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], **projektu pouze** dílčí může obsahovat další příkazy.  
  
### <a name="to-compile-multiple-c-project-items"></a>Kompilace více položek projektu C++  
  
1.  V **Průzkumníku řešení**, vyberte několik souborů, které mají může být zkompilované akce, otevřete místní nabídku pro jednu z těchto souborů a potom zvolte **zkompilovat**.  
  
    Pokud mají závislosti soubory, soubory se zkompiluje v pořadí závislostí. Operace kompilace se nezdaří, pokud tento soubor vyžaduje předkompilovaných hlaviček, který není k dispozici při kompilaci. Operaci kompilace použije aktuální konfiguraci aktivním řešení.  
  
### <a name="to-stop-a-build"></a>Chcete-li zastavit sestavení  
  
1.  Proveďte některý z následujících kroků:  
  
    -   Na řádku nabídek zvolte **sestavení**, **zrušit**.  
  
    -   Zvolte Ctrl + Break klíče.  
  
## <a name="see-also"></a>Viz také
[Postupy: zobrazení, uložit a konfigurace souborů protokolu sestavení](../ide/how-to-view-save-and-configure-build-log-files.md)   
[Získávání protokolů o sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)   
[Kompilaci a sestavování](../ide/compiling-and-building-in-visual-studio.md)   
[Principy konfigurací sestavení](../ide/understanding-build-configurations.md)   
[Konfigurace ladění a verzí projektu](http://msdn.microsoft.com/en-us/0440b300-0614-4511-901a-105b771b236e)   
[Odkaz sestavení C/C++](/cpp/build/reference/c-cpp-building-reference)   
[Přepínače příkazového řádku nástroje devenv](../ide/reference/devenv-command-line-switches.md)   
[Projekty a řešení](../ide/solutions-and-projects-in-visual-studio.md)