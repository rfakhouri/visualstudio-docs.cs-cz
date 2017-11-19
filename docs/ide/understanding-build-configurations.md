---
title: "Konfigurace sestavení Principy | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SolutionProperties.ActiveConfig
- vs.build.newprojectconfiguration
- vc.proj.configurationsctrl.multipleconfigs
- vs.build.editsolutionconfigurations
- vs.build.editprojectconfigurations
- vs.multipleconfigurations
- vs.build.newsolutionconfiguration
- VS.ConfigurationManager
- VS.MultipleConfig
helpviewer_keywords:
- solution build configurations, about build configurations
- build configurations
- project build configurations
- build configurations, advanced
- projects [Visual Studio], build configuration
- solutions [Visual Studio], build configuration
ms.assetid: 934c727d-3a22-429c-bd13-3552cecf2e24
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 003e4abaf5e6fbabead604c495b2018402cf74ec
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="understanding-build-configurations"></a>Principy konfigurací sestavení
Můžete uložit různé konfigurace vlastností řešení a projektu pro použití v různých druhů sestavení. Vytvořit, vyberte, upravit nebo odstranit konfiguraci, můžete použít **nástroje Configuration Manager**. Chcete-li jej otevřít v řádku nabídek zvolte **sestavení**, **nástroje Configuration Manager**, nebo stačí zadat **konfigurace** v **Snadné spuštění** pole. Můžete také **konfigurace řešení** seznam na **standardní** nástrojů vyberte konfiguraci, nebo otevřít **nástroje Configuration Manager**.  
  
> [!NOTE]
>  Pokud nemůžete najít řešení, nastavení konfigurace na panelu nástrojů a nemá přístup **nástroje Configuration Manager**, [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] vývoj nastavení může být použita. Další informace najdete v tématu [postupy: Správa konfigurací s Visual Basic Developer nastavení použita](../ide/how-to-manage-build-configurations-with-visual-basic-developer-settings-applied.md).  
  
 Ve výchozím nastavení, ladění a vydání konfigurace jsou zahrnuty v projektech, které jsou vytvořené pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] šablony. Podporuje konfiguraci ladění ladění aplikace a konfigurace verze sestavení verze aplikace, které se dá nasadit. Další informace najdete v tématu [postupy: nastavení ladění a vydání konfigurace](../debugger/how-to-set-debug-and-release-configurations.md). Můžete také vytvořit vlastní řešení konfigurace a konfigurace projektu. Další informace najdete v tématu [postupy: vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md).  
  
## <a name="solution-configurations"></a>Konfigurace řešení  
 Konfigurace řešení určuje, jak projekty v řešení jsou vytvořené a nasazené. -Li upravit konfiguraci řešení nebo definovat novou, v **nástroje Configuration Manager**v části **aktivní konfigurace řešení**, zvolte **upravit** nebo **nový** .  
  
 Každá položka v **projektu kontexty** pole v konfiguraci řešení představuje projekt v řešení. Pro každou kombinaci **aktivní konfigurace řešení** a **platforma Active řešení**, můžete nastavit, jak se používá každý projekt. (Další informace o řešení platformy najdete v tématu [Principy platforem sestavení](../ide/understanding-build-platforms.md).)  
  
> [!NOTE]
>  Při definování novou konfiguraci řešení a vyberte **vytvořit nové konfigurace projektu** políčko [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky přiřadí novou konfiguraci pro všechny projekty. Podobně když definovat nová platforma řešení a vyberete **vytvořit nové platformy projektu** políčko [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] automaticky přiřadí nové platformě na všechny projekty. Navíc pokud přidáte projekt, který se zaměřuje nové platformě, Visual Studio přidá do seznamu řešení platforem této platformě a přiřadí ji k všechny projekty.  
>   
>  Můžete upravovat nastavení pro každý projekt.  
  
 Konfigurace aktivního řešení taky poskytuje kontext k prostředí IDE. Například pokud pracujete na projektu a konfigurace určuje, že se budou vytvořeny pro mobilní zařízení, **sada nástrojů** zobrazí pouze položky, které lze použít v projektu mobilních zařízení.  
  
## <a name="project-configurations"></a>Konfigurace projektu  
 Konfigurace a platformy cíle projektu používají společně k určení vlastnosti, které chcete použít, když je vytvořen. Projekt může mít jiné sady definic vlastností pro každou kombinaci konfigurace a platformy. Pokud chcete upravit vlastnosti projektu, můžete jeho stránky vlastností. (V **Průzkumníku řešení**, otevřete místní nabídky projektu a zvolte **vlastnosti**.)  
  
 Pro každý projekt konfiguraci můžete definovat vlastnosti závislá na konfiguraci podle potřeby. Například pro konkrétní sestavení, můžete nastavit, které položky projektu budou zahrnuty, a výstup souborů bude vytvořen, kde budou umístěny, a jak bude optimalizované.  
  
 Konfigurace projektu se může značně lišit. Vlastnosti jednu konfiguraci může například určit, že svůj výstupní soubor optimalizována tak, aby zabíral minimální místo, zatímco jiné konfigurace mohla uvádět, že jeho spustitelný soubor spouští maximální rychlostí.  
  
 Konfigurace projektu se uloží řešení – není uživatelem – tak, aby bylo možné sdílet týmem.  
  
 I když závislosti projektu jsou nezávislé na konfiguraci, budou vytvořeny pouze projektů, které jsou určené v aktivním řešení konfigurace.  
  
## <a name="how-visual-studio-assigns-project-configurations"></a>Jak přiřadí konfigurace projektu Visual Studio  
 Při definování novou konfiguraci řešení a nemáte Kopírovat nastavení z existující sady Visual Studio používá následující kritéria přiřadit výchozí konfigurace projektu. Kritéria jsou vyhodnocovány v uvedeném pořadí.  
  
1.  Pokud má název konfigurace projektu (*\<název konfigurace > \<název platformy >*), je přiřazen přesně odpovídá názvu se nová konfigurace řešení, aby konfigurace. Názvy konfigurace nerozlišují malá a velká písmena.  
  
2.  Pokud projekt má název konfigurace, ve kterém název konfigurace část odpovídá novou konfiguraci řešení, tato konfigurace je přiřazená, jestli odpovídá části platformy, nebo ne.  
  
3.  Pokud ještě není nalezena žádná shoda, je přiřazen první konfigurace, která je uvedena v projektu.  
  
## <a name="how-visual-studio-assigns-solution-configurations"></a>Jak přiřadí konfigurace řešení sady Visual Studio  
 Při vytváření konfigurace projektu (v **nástroje Configuration Manager**, výběrem **nový** v rozevírací nabídce v **konfigurace** sloupec pro tento projekt) a Vyberte **vytvořit nové konfigurace řešení** zaškrtávací políčko, Visual Studio hledá konfigurace s názvem jako řešení pro sestavení projektu na jednotlivých platformách podporuje. V některých případech Visual Studio přejmenuje stávající konfigurace řešení nebo definuje nové.  
  
 Visual Studio používá následující kritéria přiřadit konfigurace řešení.  
  
-   Pokud konfigurace projektu neurčuje platformu nebo určuje právě jednu platformu, pak konfigurace řešení, jehož název se shoduje s novou konfigurací projektu je buď najít nebo přidat. Výchozí název této konfigurace řešení nezahrnuje název platformy; používá formát  *\<konfigurace název projektu >*.  
  
-   Pokud projekt podporuje více platforem, konfigurace řešení je najít nebo přidat pro každou podporovanou platformu. Název každé konfiguraci řešení zahrnuje konfiguraci název projektu a název platformy a má tvar  *\<konfigurace název projektu > \<název platformy >*.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření aplikace](../ide/walkthrough-building-an-application.md)   
 [Kompilaci a sestavování](../ide/compiling-and-building-in-visual-studio.md)   
 [Projekty a řešení](../ide/solutions-and-projects-in-visual-studio.md)   
 [Odkaz sestavení C/C++](/cpp/build/reference/c-cpp-building-reference)   
 [Přepínače příkazového řádku nástroje devenv](../ide/reference/devenv-command-line-switches.md)