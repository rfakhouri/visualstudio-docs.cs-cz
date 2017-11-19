---
title: "Návod: Vytvoření vlastní stránky aktivit pracovního postupu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- custom workflow activities [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, custom workflow activities
- site workflows [SharePoint development in Visual Studio]
- workflow activities [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, site workflows
ms.assetid: 8219a779-c27b-4186-92c9-5bda03328aa9
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6d3579c3d537dc13723cbe285b454b24d079fe1f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-create-a-custom-site-workflow-activity"></a>Návod: Vytvoření vlastní aktivity pracovního postupu na webu
  Tento návod ukazuje, jak vytvořit vlastní aktivity pracovního postupu úrovni webu použití [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. (Pracovních postupů na úrovni lokality se vztahují na celý web, ne jenom seznam v lokalitě.) Vlastní aktivity vytvoří zálohu seznam oznámení a pak zkopíruje obsah seznamu oznámení do ní.  
  
 Tento návod ukazuje následující úlohy:  
  
-   Vytvoření pracovního postupu úrovni webu.  
  
-   Vytvoření vlastního pracovního postupu aktivity.  
  
-   Vytváření a odstraňování seznamu služby SharePoint.  
  
-   Kopírování položek seznamu jednoho do jiného.  
  
-   Zobrazení seznamu v panel Rychlé spuštění.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   Podporované edice systému [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] a služby SharePoint. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
## <a name="creating-a-site-workflow-custom-activity-project"></a>Vytvoření projektu vlastní aktivity pracovního postupu lokality  
 Nejprve vytvořte projekt k uložení a otestovat vlastní pracovní postup aktivity.  
  
#### <a name="to-create-a-site-workflow-custom-activity-project"></a>Vytvoření projektu vlastní aktivity pracovního postupu lokality  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu** zobrazíte **nový projekt** dialogové okno.  
  
2.  Rozbalte **SharePoint** uzel v rámci buď **Visual C#** nebo **jazyka Visual Basic**a potom zvolte **2010** uzlu.  
  
3.  V **šablony** podokně, vyberte **projektu služby SharePoint 2010** šablony.  
  
4.  V **název** zadejte **AnnouncementBackup**a potom zvolte **OK** tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** se zobrazí.  
  
5.  Na **zadejte úroveň lokality a zabezpečení pro ladění** vyberte **nasadit jako řešení farmy** možnost tlačítko a potom vyberte **Dokončit** tlačítko tak, aby přijímal úroveň a výchozí web vztah důvěryhodnosti.  
  
     Tento krok nastaví úroveň důvěryhodnosti pro řešení jako řešení farmy, k dispozici jenom možnost pro projekty pracovního postupu.  
  
6.  V **Průzkumníku řešení**, vyberte uzel projektu a potom na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
7.  V části buď **Visual C#** nebo **jazyka Visual Basic**, rozbalte **SharePoint** uzel a potom vyberte **2010** uzlu.  
  
8.  V **šablony** podokně, vyberte **sekvenční pracovní postup (pouze řešení farmy)** šablony a potom zvolte **přidat** tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** se zobrazí.  
  
9. Na **zadejte název pracovního postupu pro ladění** přijměte výchozí název (AnnouncementBackup - Workflow1). Změnit typ šablony pracovního postupu na **pracovní postup webu**a potom zvolte **Další** tlačítko.  
  
10. Vyberte **Dokončit** tlačítko tak, aby přijímal zbývající výchozí nastavení.  
  
## <a name="adding-a-custom-workflow-activity-class"></a>Přidání třídy aktivity vlastní pracovní postup  
 V dalším kroku přidejte třídu do projektu obsahuje kód pro aktivitu vlastní pracovní postup.  
  
#### <a name="to-add-a-custom-workflow-activity-class"></a>Přidání třídy aktivity vlastní pracovní postup  
  
1.  Na řádku nabídek zvolte **projektu**, **přidat novou položku** zobrazíte **přidat novou položku** dialogové okno.  
  
2.  V **nainstalovaných šablonách** stromové zobrazení, vyberte **kód** uzel a potom zvolte **– třída** šablony v seznamu šablon položek projektu. Použijte výchozí název Class1. Vyberte **přidat** tlačítko.  
  
3.  Nahraďte kód v Class1 následující:  
  
     [!code-csharp[SP_AnnBackup#1](../sharepoint/codesnippet/CSharp/announcementbackup/class1.cs#1)]
     [!code-vb[SP_AnnBackup#1](../sharepoint/codesnippet/VisualBasic/announcementbackupvb/class1.vb#1)]  
  
4.  Uložte projekt a potom na řádku nabídek zvolte **sestavení**, **sestavit řešení**.  
  
     Class1 se zobrazí jako vlastní akce v **sada nástrojů** na **AnnouncementBackup součásti** kartě.  
  
## <a name="adding-the-custom-activity-to-the-site-workflow"></a>Přidání vlastní aktivitu do pracovního postupu lokality  
 V dalším kroku přidáte aktivitu do pracovního postupu tak, aby obsahovala vlastní kód.  
  
#### <a name="to-add-a-custom-activity-to-the-site-workflow"></a>Chcete-li přidat vlastní aktivity k webu pracovního postupu  
  
1.  Otevřete Workflow1 v Návrháři pracovních postupů v zobrazení návrhu.  
  
2.  Přetáhněte Class1 z **sada nástrojů** tak, aby se v části `onWorkflowActivated1` aktivity nebo otevřete místní nabídky pro Class1, zvolte **kopie**, otevřete místní nabídku pro řádek v části `onWorkflowActivated1` aktivity a potom zvolte **vložení**.  
  
3.  Uložte projekt.  
  
## <a name="testing-the-site-workflow-custom-activity"></a>Testování webu vlastní aktivity pracovního postupu  
 Potom spusťte projekt a spusťte pracovní postup webu. Vlastní aktivity vytvoří zálohování seznam oznámení a zkopíruje obsah z aktuální seznam oznámení do ní. Kód také zkontroluje, zda zálohování seznamu před vytvořením jedna již existuje. Pokud zálohování seznamu již existuje, je odstraněn. Kód také přidá odkaz na nový seznam na panel Rychlé spuštění webu služby SharePoint.  
  
#### <a name="to-test-the-site-workflow-custom-activity"></a>K testování webu vlastní aktivity pracovního postupu  
  
1.  Zvolte klávesy F5 spusťte projekt a nasaďte ho do služby SharePoint.  
  
2.  Na panel Rychlé spuštění, zvolte **uvádí** odkaz zobrazíte všechny seznamy, které jsou k dispozici na webu služby SharePoint. Všimněte si, že je pouze jeden seznam pro oznámení s názvem **oznámení**.  
  
3.  V horní části na webovou stránku služby SharePoint, vyberte **pracovní postupy uzlu** odkaz.  
  
4.  V části spuštění oddíl nový pracovní postup, vyberte **AnnouncementBackup - Workflow1** odkaz. To spustí pracovní postup webu a spouští kód ve vlastní akci.  
  
5.  Na panel Rychlé spuštění, zvolte **zálohování oznámení** odkaz. Všimněte si, že všechna oznámení, které jsou součástí **oznámení** seznamu byly zkopírovány do tohoto nového seznamu.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytvoření přijímače událostí](../sharepoint/how-to-create-an-event-receiver.md)   
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  