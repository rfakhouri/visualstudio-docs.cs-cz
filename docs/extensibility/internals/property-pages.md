---
title: "Stránky vlastností | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration options, changing properties
- property pages
- property pages, changing configuration options
ms.assetid: b9b3e6e8-1e30-4c89-9862-330265dcf38c
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: cedf021321b66c47690450823a7da92cd19888eb
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="property-pages"></a>Stránky vlastností
Uživatelé mohou zobrazit a změnit vlastnosti závislá na konfiguraci a - nezávislé projektu pomocí stránky vlastností. A **stránky vlastností** tlačítko je k dispozici v **vlastnosti** okno nebo na panelu nástrojů Průzkumníku řešení pro objekty, které poskytují zobrazení stránky vlastnosti vybraného objektu. Stránky vlastností jsou vytvořené pomocí prostředí a jsou dostupné pro projekty a řešení. Mohou, ale být k dispozici pro položky projektu, které používají závislá na konfiguraci vlastností. Tato funkce může použít, pokud soubory v rámci projektu vyžadují různé kompilátoru přepínač nastavení k vytvoření správně.  
  
## <a name="using-property-pages"></a>Pomocí stránky vlastností  
 Pokud je již zobrazen stránce vlastností a výběr změní (například z řešení do projektu), informace zobrazené v změny stránky se zobrazí vlastnosti pro výběr nového. Pokud nejsou k dispozici žádné vlastnosti v objektu, které podporují stránky vlastností, je prázdná stránka vlastností.  
  
 Pokud je vybráno více objektů, zobrazí stránku vlastností průnik vlastností pro všechny vybrané položky. Pokud vybraná položka neobsahuje vlastnosti závislá na konfiguraci a **stránky vlastností** po kliknutí na tlačítko na panelu nástrojů Průzkumníka řešení, změní fokus do okna vlastností. Další informace týkající se vlastnosti – okno a výběr najdete v tématu [rozšíření vlastnosti](../../extensibility/internals/extending-properties.md).  
  
 Pokud se zobrazí vlastnosti pro více objektů a změnit hodnotu na stránce vlastnosti, všechny hodnoty pro objekty jsou nastavené na novou hodnotu i v případě, že byly původně různých a stránka byla prázdné, když se zobrazí vlastnosti jednotlivého objektu.  
  
 Existují dvě obecné typy **ProjectProperty stránky** dialogových oknech k dispozici v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. V první pro projekty Visual Basic například stránky vlastností jsou zobrazené formátu pole, jak je znázorněno na následujícím snímku obrazovky. Za sekundu zobrazit později v této části, vlastnost hostitele stránky mřížky vlastnosti podobná naleznete v okně Vlastnosti.  
  
 ![Visual Basic – stránky vlastností](../../extensibility/internals/media/vsvbproppages.gif "vsVBPropPages")  
Dialogové okno stránky vlastností projektu s pole formátu a stromové struktury  
  
 Stromové struktury v dialogovém okně Vlastnosti stránky není vytvořená s využitím <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>. V prostředí založené na úrovni názvu předaný pomocí <xref:Microsoft.VisualStudio.OLE.Interop.ISpecifyPropertyPages> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsPropertyPage> rozhraní, vytvoří se.  
  
 Nejsou k dispozici na nejvyšší úrovně pouze dvě kategorie [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] stránky vlastností:  
  
-   Běžné vlastnosti, které zobrazí nezávislé na konfigurační informace pro vybraný objekt nebo objekty. Výsledkem je když je vybrána jedna z podkategorií společných vlastností, možnosti konfigurace, platformy a Configuration Manager v horní části dialogového okna nejsou k dispozici.  
  
-   Vlastnosti konfigurace, která obsahuje závislá na konfiguraci informace týkající se ladění, optimalizace a sestavení parametry pro řešení nebo projektu.  
  
 Nelze vytvořit žádné další nejvyšší úrovně kategorie, ale můžete nechcete zobrazit jednu nebo druhou v vaši implementaci `IVsPropertyPage`. Pokud například nemáte žádné vlastnosti nezávislé konfigurace k zobrazení pro objekt, můžete nechcete zobrazit kategorie společných vlastností. Pokud se zobrazí běžné vlastnosti `ISpecifyPropertyPages` je implementována z objektu položky Procházet a vlastnosti konfigurace, pokud budete implementovat `ISpecifyPropertyPages` v objektu konfigurace (implementace objektu `IVsCfg`, `IVsProjectCfg`a související rozhraní).  
  
 Každá kategorie se zobrazí v rámci kategorií nejvyšší úrovně představuje samostatný vlastnost stránku. Určuje kategorii a podkategorie položky k dispozici v dialogovém okně vaši implementaci `ISpecifyPropertyPages` a `IVsPropertyPage`.  
  
 `IDispatch`objekty pro položky v kontejneru výběru, které mají vlastnosti, který se má zobrazit na vlastnost stránky implementace `ISpecifyPropertyPages` se vytvořit výčet seznamu ID tříd. ID třídy jsou předány jako proměnné, které chcete `ISpecifyPropertyPages` a slouží k vytvoření instance stránky vlastností. Seznam ID tříd také předaný `IVsPropertyPage` vytvoření stromové struktury nalevo od dialogové okno. Stránky vlastností pak předejte informace zpět do `IDispatch` objekt, který implementuje `ISpecifyPropertyPages` a výplní informace na každé stránce.  
  
 Vlastnosti objektu Procházet se načítají pomocí `IDispatch` pro každý objekt v kontejneru výběr.  
  
 Implementace `Help::DisplayTopicFromF1Keyword` ve vašem VSPackage poskytuje funkce pro tlačítko Nápověda.  
  
 Další informace najdete v tématu `IDispatch` a `ISpecifyPropertyPages`v knihovně MSDN.  
  
 Druhý typ stránky vlastností zobrazí v hostitelích ukázky formuláře mřížky vlastnosti, jak je znázorněno na následujícím snímku obrazovky.  
  
 ![Stránky určeno VC](../../extensibility/internals/media/vsvcproppages.gif "vsVCPropPages")  
Dialogové okno stránky vlastností s mřížky vlastností  
  
 Rozhraní `IVSMDPropertyBrowser` a `IVSMDPropertyGrid` (deklarované v vsmanaged.h) slouží k vytvoření a naplnění mřížku vlastností v rámci nebo dialogovém okně.  
  
 Architektura projekty značně změnil od minulých verzí nástroje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Konkrétně je znalost problematicky kterému projektu aktivní došlo ke změně. V [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], neexistuje žádná koncepce aktivního projektu. V předchozí vývojových prostředí aktivní projekt se, že by výchozí projekt, který sestavení a nasazení příkazy bez ohledu na kontextu. Nyní řešení ovládací prvky a řeší, která sestavení a nasazení příkazy použít pro určité projekty.  
  
 Co dříve aktivní projekt je nyní zaznamenaná v jednom ze tří způsobů:  
  
-   Projekt po spuštění  
  
     Můžete zadat projektu nebo projekty, na stránce vlastností na řešení, který bude spuštěn, když uživatel stiskne klávesu F5 nebo vybere spustit z nabídky sestavení. Toto funguje ve staré aktivní projekt v tom smyslu, že její název se zobrazí v Průzkumníku řešení s tučným písmem podobným způsobem.  
  
     Můžete načíst projekt po spuštění jako vlastnost v modelu automatizace voláním `DTE.Solution.SolutionBuild.StartupProjects`. Ve VSPackage zavoláte <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2.get_StartupProject%2A> nebo <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2.get_StartupProject%2A> metody. `IVsSolutionBuildManager`je k dispozici jako služby pomocí `QueryService` na SID_SVsSolutionBuildManager. Další informace najdete v tématu [objekt konfigurace projektu](../../extensibility/internals/project-configuration-object.md) a [konfigurace řešení](../../extensibility/internals/solution-configuration.md).  
  
-   Konfigurace sestavení řešení Active  
  
     [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]má aktivní řešení konfigurace k dispozici v modelu automatizace implementací `DTE.Solution.SolutionBuild.ActiveConfiguration`. Konfigurace řešení je kolekce, která obsahuje jednu konfiguraci projektu pro každý projekt v řešení (každý projekt, může mít víc konfigurací ve více platformách s odlišnými názvy). Další informace týkající se stránky vlastností na řešení, najdete v části [konfigurace řešení](../../extensibility/internals/solution-configuration.md).  
  
-   Projekt aktuálně vybraný.  
  
     Implementace <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCurrentSelection%2A> metoda pro načtení projektu hierarchie a položka projektu nebo vybrané položky. Z prostředí DTE, použijte `SelectedItems.SelectedItem.Project` a `SelectedItems.SelectedItem.ProjectItem` metody. Je ukázkový kód těchto položek základní [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] dokumenty.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPropertyPage>   
 [Správa možnosti konfigurace](../../extensibility/internals/managing-configuration-options.md)   
 [Objekt konfigurace projektu](../../extensibility/internals/project-configuration-object.md)   
 [Konfigurace řešení](../../extensibility/internals/solution-configuration.md)