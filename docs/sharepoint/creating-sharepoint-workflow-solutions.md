---
title: Vytváření řešení pracovního postupu služby SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VSTO.NewSharePointWorkflowWizard.Page3
- VS.SharePointTools.Workflow.WorkflowName
- VSTO.NewSharePointWorkflowWizard.Page2
- VSTO.NewSharePointWorkflowWizard.Page1
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, workflows
- workflows [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: bc78726146b67a39f8e8988dda6c7d2baf5c49b3
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34691921"
---
# <a name="creating-sharepoint-workflow-solutions"></a>Vytváření řešení pracovního postupu služby SharePoint
  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] poskytuje nástroje, které vám pomohou vytvořit vlastní pracovní postupy, které spravují životní cyklus dokumenty a vypisovat položky ve webovém serveru SharePoint. Zadat položky zahrnují návrháře, sadu ovládacích prvků aktivity a odkazy na sestavení nezbytné. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] zahrnuje také **Průvodce vlastním nastavením SharePoint**, vám pomůžou vytvořit a konfigurovat pracovní postupy.  
  
 Seznam požadovaných součástí pro vytváření projektů služby SharePoint v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], najdete v části [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md). Další informace o SharePoint, naleznete v části [Microsoft produkty a technologie SharePoint](http://go.microsoft.com/fwlink/?LinkId=178470).  
  
## <a name="workflows-in-sharepoint"></a>Pracovní postupy ve službě SharePoint  
 Když přidáte pracovní postup k seznamu nebo knihovny služby SharePoint, můžete vynutit obchodní proces na všechny položky v seznamu nebo knihovny. Pracovní postup popisuje akce, které systém nebo uživatelé musí provést na každou položku, například odeslání položku upravit a poté zkontrolovat. Tyto akce, označuje jako *aktivity*, představují stavební kameny pracovního postupu.  
  
 Můžete vytvořit pracovních postupů služby SharePoint v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] a nasadit je na webovém serveru SharePoint. Po nasazení pracovního postupu do služby SharePoint můžete přiřadit k do knihovny nebo seznamu. Ho můžete potom automaticky spustit, proces, nebo ručně uživatelem. Další informace o operaci pracovního postupu najdete v tématu [pracovních postupů služby SharePoint vývoj pomocí sady Visual Studio](https://docs.microsoft.com/sharepoint/dev/general-development/develop-sharepoint-workflows-using-visual-studio).  
  
## <a name="create-custom-sharepoint-workflows"></a>Vytvoření vlastních pracovních postupů služby SharePoint
 Dva projekty pracovního postupu služby SharePoint jsou k dispozici v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]: **sekvenční pracovní postup** a **pracovní postup stavového stroje**.  
  
 A *sekvenční pracovní postup* představuje sérii kroků. Kroky se jedna po druhé, dokud nebude dokončena poslední aktivita. Sekvenční pracovní postupy jsou vždy výhradně sekvenční při jejich provádění. Protože můžou přijímat externí události a zahrnovat paralelní logiku toky, se může lišit přesný pořadí zpracování. Následující obrázek znázorňuje příklad sekvenčního pracovního postupu.  
  
 ![Sekvenční pracovní postup](../sharepoint/media/sp-sequential.png "sekvenční pracovní postup")  
  
 A *pracovní postup stavového stroje* představuje sadu stavy a přechody, akce. Kroky v pracovním postupu stavu počítače spustit asynchronně. To znamená, že se neprovádí nutně jedna po druhé, ale místo toho jsou aktivovány akce a stavy. Jeden stav je přiřazen jako počáteční stav, a potom založené na události, je proveden přechod na jiný stav. Stav počítač může mít konečný stav, který určuje konec pracovního postupu. Následující diagram ukazuje příklad pracovního postupu stav počítače.  
  
 ![Stav pracovního postupu počítač](../sharepoint/media/sp-state.png "stavu počítače pracovního postupu")  
  
 Další informace o typech pracovního postupu najdete v tématu [pracovního postupu typy](http://go.microsoft.com/fwlink/?LinkId=178995).  
  
### <a name="using-the-wizard"></a>Pomocí Průvodce
 Při vytváření projektu pracovního postupu služby SharePoint v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], nejprve určit nastavení v **Průvodce vlastním nastavením SharePoint**. Toto nastavení používá průvodce k vytvoření projektu v **Průzkumníku řešení**. Tento projekt obsahuje soubor kódu několik souborů, které jsou používány k nasazení pracovního postupu, a odkazuje na sestavení, které jsou nutné k vytvoření vlastního pracovního postupu služby SharePoint.  
  
 Po vytvoření pracovního postupu, můžete upravit jeho vlastnosti v okně Vlastnosti. I když většina vlastnosti pracovního postupu můžete změnit přímo v okně vlastností, některé vyžadují, abyste klikněte na tlačítko se třemi tečkami (![ASP.NET – Návrhář mobilních řešení elipsy](../sharepoint/media/mwellipsis.gif "ASP.NET – Návrhář mobilních řešení elipsy")) na změňte jejich hodnot. Toto tlačítko restartuje **Průvodce vlastním nastavením SharePoint**. Poté, co provedete vlastnost hodnotu změny, vyberte **Dokončit** tlačítko pro jejich dokončení.  
  
> [!NOTE]  
>  **Typ pracovního postupu** vlastnost je jen pro čtení a nedá se změnit. Pokud chcete změnit typ pracovního postupu, musíte vytvořit jiný pracovní postup.  
  
## <a name="design-a-sharepoint-workflow"></a>Návrh pracovního postupu služby SharePoint
 Po definování všechny kroky v obchodní proces, pomocí [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Návrhář postupu provádění návrhu pracovního postupu služby SharePoint. Chcete-li otevřít návrháře, dvakrát klikněte na Workflow1.cs nebo Workflow1.vb v **Průzkumníku řešení**, nebo otevřete místní nabídku pro některý z těchto souborů a potom vyberte **otevřete**.  
  
### <a name="activities"></a>Aktivity  
 K návrhu pracovního postupu, přidání aktivit z **sada nástrojů** k *pracovní postup plánu* v designeru. Pracovní postup plánu obsahuje posloupnost aktivit v pořadí, že má být provedena.  
  
 Existují dva typy aktivit:  
  
-   *Jednoduché aktivity* provést jedné jednotky práce, například jako "zpoždění 1 den" nebo "spuštění webové služby."  
  
-   *Složené aktivity* obsahovat další aktivity, například aktivitu podmíněného může obsahovat dvě větve.  
  
 Oba typy aktivit jsou k dispozici v **sada nástrojů**.  
  
 Aktivity může mít vlastnosti, metod a události. Použití **vlastnosti** okna a nastavte vlastnosti aktivity.  
  
 Můžete také vytvořit vlastní aktivity. Další informace najdete v tématu [návod: vytvoření vlastní aktivity pracovního postupu lokality](../sharepoint/walkthrough-create-a-custom-site-workflow-activity.md).  
  
 Aktivity jsou uspořádány v následujících karet v **sada nástrojů**:  
  
-   **Pracovního postupu služby SharePoint**  
  
-   **V3.0 pracovního postupu systému Windows**  
  
-   **Windows Workflow v3.5**  
  
 Ne všechny aktivity pracovního postupu základní jsou podporované službou SharePoint. Další informace najdete v tématu [přehled pracovního postupu aktivit pro Windows SharePoint Services](http://go.microsoft.com/fwlink/?LinkID=156094).  
  
#### <a name="sharepoint-workflow-activities"></a>Aktivity pracovního postupu služby SharePoint
 **Pracovního postupu služby SharePoint** karty obsahovat specializované aktivity pro použití v [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)]. Tyto aktivity zjednodušit a zefektivnit vývoje pracovních životního cyklu dokumentů. Další informace o aktivitách uvedené v **pracovního postupu služby SharePoint** kartě najdete v tématu [přehled pracovního postupu aktivit pro Windows SharePoint Services](http://go.microsoft.com/fwlink/?LinkID=156094).  
  
#### <a name="windows-workflow-activities"></a>Aktivity pracovního postupu systému Windows
 **Windows Workflow** karty obsahovat aktivity, které jsou poskytovány [!INCLUDE[TLA#tla_workflow](../sharepoint/includes/tlasharptla-workflow-md.md)]. Tyto aktivity slouží k vytvoření pracovního postupu plány pro jakýkoli druh aplikace pracovního postupu systému Windows.  
  
 Další informace o aktivitách uvedené v **pracovními postupy prostředí Windows** kartě najdete v tématu [Windows Workflow Foundation aktivity](http://go.microsoft.com/fwlink/?LinkID=156096). Další informace o Windows Workflow Foundation, najdete v části [Windows Workflow Foundation – přehled](http://go.microsoft.com/fwlink/?LinkID=128632).  
  
### <a name="work-with-activities-in-the-designer"></a>Práce s aktivitami v Návrháři
 Plán pracovní postup může obsahovat kombinaci pracovního postupu systému Windows a aktivity pracovního postupu služby SharePoint.  
  
 Návrhář zobrazí vizuální upozornění můžete umístit a konfigurovat aktivity správně. Když přetáhněte nebo zkopírujte aktivitu do pracovního postupu plán, Návrhář zobrazí zelená znaménko plus (+) ikony, které ukazují platná umístění pro danou aktivitu v pracovním postupu. Aktivitu nelze umístit na místě, kde nebude platný. Například nelze umístit aktivitu odesílání jako první aktivitu ve větvi naslouchání aktivity. Další informace najdete v tématu [SharePoint Designer Developer Center](http://go.microsoft.com/fwlink/?LinkId=178476).  
  
## <a name="collect-information-during-the-workflow"></a>Shromáždění informací o během pracovního postupu
 Můžete chtít shromažďovat informace od uživatelů v předdefinované časy v pracovním postupu. Můžete shromáždit informace pomocí formulářů nebo vlastnosti položky.  
  
### <a name="forms"></a>Formuláře  
 Formuláře jsou jako dialogových oken, které obsahují otázky a nabízejí způsoby uživatelům poskytnout odpovědi.  
  
 Existují čtyři typy formuláře, které lze použít v pracovním postupu:  
  
-   Přidružení  
  
-   Inicializace  
  
-   Úpravy  
  
-   Úloha  
  
 Z těchto [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] zahrnuje šablony položek, formulářů přidružení a inicializace. Příklad *formuláře přidružení* je ten, který umožňuje správcům instalaci pracovního postupu zadejte parametry, které se vztahují k pracovní postup, jako je například limitu útraty pro pracovní postup náklady. Příklad *formuláře inicializace* je ten, který umožňuje uživateli pracovního postupu náklady zadejte množství, které budou stráví do pracovního postupu. Další informace o těchto typech forms najdete v tématu [projektu služby SharePoint a šablony položek projektu](../sharepoint/sharepoint-project-and-project-item-templates.md).  
  
### <a name="item-properties"></a>Vlastnosti položky
 Může taky shromažďovat informace od uživatelů pomocí vlastností položky v seznamu nebo knihovny služby SharePoint. K souboru hlavní kódu (Workflow1.cs nebo Workflow1.vb) deklaruje instance třídy Microsoft.SharePoint.Workflow.SPWorkflowActivationProperties.WorkflowProperties s názvem `workflowProperties`. Použití `workflowProperties` objekt, který má přístup k vlastnostem do knihovny nebo seznamu v kódu. Příklad, naleznete v části [návod: vytváření a ladění řešení pracovního postupu služby SharePoint](../sharepoint/walkthrough-creating-and-debugging-a-sharepoint-workflow-solution.md).  
  
## <a name="debug-a-sharepoint-workflow-template"></a>Ladění šablonu pracovního postupu služby SharePoint
 Můžete ladit projektu pracovního postupu služby SharePoint stejná jako jiné ladění [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] webové projekty. Při spuštění [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ladicí program, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] používá nastavení, které zadáte v **Průvodce vlastním nastavením SharePoint** otevřít na příslušný web služby SharePoint a automaticky spojovat šablonu pracovního postupu s příslušnou knihovnu nebo seznamu. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] také připojí [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ladicího programu k [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] procesu w3wp.exe s názvem.  
  
 K testování pracovního postupu, je nutné jej spustit ručně. Další informace najdete v části "Ladění pracovních postupech" v [ladění řešení služby SharePoint](../sharepoint/debugging-sharepoint-solutions.md). Další informace o [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] webové ladění aplikací najdete v tématu [ladění webových aplikací a skriptu](/visualstudio/debugger/debugging-web-applications-and-script).  
  
## <a name="deploy-a-sharepoint-workflow-template"></a>Nasazení šablony pracovního postupu služby SharePoint
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Projekty SharePoint pracovního postupu nasadit stejně jako jiný [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projektů služby SharePoint. Další informace najdete v tématu [balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md).  
  
## <a name="import-globally-reusable-workflows"></a>Importovat globální znovu použitelné pracovní postupy
 Kromě vytváření pro danou lokalitu znovu použitelné pracovní postupy, návrháře služby SharePoint můžete vytvořit *globálně znovu použitelné pracovní postupy*, které jsou pracovní postupy, které můžete používat libovolný web služby SharePoint. Projekt Import opakovaně použitelného pracovního postupu v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] aktuálně neimportuje globálně znovu použitelné pracovní postupy. Však můžete buď použijte k převedení globálně opakovaně použitelného pracovního postupu do opakovaně použitelného pracovního postupu návrháře služby SharePoint, nebo importovat pracovní postup jako nepřevedeném deklarativní pracovního postupu. Další informace najdete v tématu [import položek z existující stránky SharePoint](../sharepoint/importing-items-from-an-existing-sharepoint-site.md).  
  
## <a name="related-topics"></a>Související témata
  
|Název|Popis|  
|-----------|-----------------|  
|[Návod: Vytváření a ladění řešení pracovního postupu služby SharePoint](../sharepoint/walkthrough-creating-and-debugging-a-sharepoint-workflow-solution.md)|Vás provede procesem vytváření a ladění jednoduchou [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] pracovního postupu.|  
|[Návod: Vytvoření pracovního postupu pomocí formulářů přidružení a inicializace](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)|Vás krok za krokem k vytvoření více plnohodnotné [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] dokončení pracovního postupu pomocí formulářů přidružení a inicializace.|  
|[Návod: Přidání stránky aplikace do pracovního postupu](../sharepoint/walkthrough-add-an-application-page-to-a-workflow.md)|Staví na tématu [návod: vytvoření pracovního postupu pomocí formulářů přidružení a inicializace](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md) přidáním stránku aplikace Další .aspx, která hlásí data zadaná do pracovního postupu.|  
|[Návod: Vytvoření vlastní aktivity pracovního postupu na webu](../sharepoint/walkthrough-create-a-custom-site-workflow-activity.md)|Ukazuje, jak provádět úlohy dvou klíčů: vytvoření pracovního postupu úrovni webu a vytvořit vlastní pracovní postup aktivitu.|  
|[Návod: Import opakovaně použitelného pracovního postupu návrháře služby SharePoint do sady Visual Studio](../sharepoint/walkthrough-import-a-sharepoint-designer-reusable-workflow-into-visual-studio.md)|Ukazuje, jak importovat opakovaně použitelný deklarativní pracovní postupy vytvořené v SharePoint Designer 2010 do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projektu služby SharePoint.|  
  
## <a name="see-also"></a>Viz také:
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)   
 [Sestavování a ladění řešení služby SharePoint](../sharepoint/building-and-debugging-sharepoint-solutions.md)   
 [Vytváření stránek aplikací pro službu SharePoint](../sharepoint/creating-application-pages-for-sharepoint.md)  
  
 