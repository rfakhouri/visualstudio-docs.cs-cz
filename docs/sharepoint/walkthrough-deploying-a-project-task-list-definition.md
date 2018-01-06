---
title: "Návod: Nasazení definice seznamu úkolů projektu | Microsoft Docs"
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
helpviewer_keywords: SharePoint development in Visual Studio, deploying
ms.assetid: 18b62016-ed30-4dd1-9dfc-0d7e82c6767f
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 16cccaf9a8639ef2d7213140121b087cd15e72d2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-deploying-a-project-task-list-definition"></a>Postupy: Nasazení definice seznamu úloh projektu
  Tento postup vám ukáže, jak používat [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)] Pokud chcete vytvořit, upravit, ladění a nasazení seznam serveru SharePoint ke sledování úloh projektu.  
  
 Tento návod znázorňuje následující úlohy:  
  
-   [Vytváření seznamu služby SharePoint](#CreatingListDef).  
  
-   [Vytváření seznamu služby SharePoint](#CreatingListDef).  
  
-   [Přidání příjemce událostí](#AddEventRcvr).  
  
-   [Přizpůsobení funkcí seznamu úkolů projektu](#CustomizeFeature).  
  
-   [Seznam úkolů sestavení a testování projektu](#BuildTest).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   Podporované edice systému Microsoft Windows a služby SharePoint. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!INCLUDE[vs_pro_current_short](../sharepoint/includes/vs-pro-current-short-md.md)]nebo edici nástroje Visual Studio Application Lifecycle Management (ALM).  
  
##  <a name="CreatingListDef"></a>Vytváření seznamu služby SharePoint  
 Vytvořte seznam projektu služby SharePoint a přidružte definice seznamu úloh.  
  
#### <a name="to-create-a-sharepoint-list-project"></a>Chcete-li vytvořit seznam projektu služby SharePoint  
  
1.  Otevřete **nový projekt** dialogové okno, rozbalte seznam **SharePoint** uzel a potom zvolte **2010** uzlu.  
  
2.  V **šablony** podokně, vyberte **projektu služby SharePoint 2010** šablony, název projektu **ProjectTaskList**a potom vyberte **OK**tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** se zobrazí.  
  
3.  Zadejte místní web služby SharePoint, který používáte pro ladění, vyberte **nasadit jako řešení farmy** možnost tlačítko a potom vyberte **Dokončit** tlačítko.  
  
4.  Otevřete místní nabídky projektu a zvolte **přidat**, **novou položku**.  
  
5.  V **šablony** podokně, vyberte **seznamu** šablony a potom zvolte **přidat** tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** se zobrazí.  
  
6.  V **zadejte název chcete k zobrazení seznamu?** zadejte **seznamu úkolů projektu**.  
  
7.  Vyberte **vytvořit seznam nepřizpůsobitelné na základě existující typu seznamu** možnost tlačítko a zvolte ve svém seznamu **úlohy**a potom zvolte **Dokončit** tlačítko.  
  
     Seznam, funkce a balíku objeví v **Průzkumníku řešení**.  
  
##  <a name="AddEventRcvr"></a>Přidání přijímače událostí  
 V seznamu úkolů, můžete přidat příjemce událostí, který automaticky nastaví splatnosti datum a popis úlohy. Následující postup obslužnou rutinu jednoduchá událost přidá do seznamu instance jako přijímače událostí.  
  
#### <a name="to-add-an-event-receiver"></a>Chcete-li přidat přijímače událostí  
  
1.  Otevřete místní nabídce uzlu projektu, zvolte **přidat**a potom zvolte **novou položku**.  
  
2.  V seznamu šablon služby SharePoint, vyberte **příjemce událostí** šablony a pojmenujte ji **ProjectTaskListEventReceiver**.  
  
     **Průvodce vlastním nastavením SharePoint** se zobrazí.  
  
3.  Na **zvolte nastavení příjemce událostí** vyberte **události položky seznamu** jako typ příjemce událostí v **jaký typ příjemce událostí chcete** seznamu.  
  
4.  V **co položka by měl být zdroj události** vyberte **úlohy**.  
  
5.  V seznamu událostí pro zpracování, zaškrtněte políčko vedle **přidání položky**a potom zvolte **Dokončit** tlačítko.  
  
     Nový uzel příjemce událostí se přidá do projektu s souboru kódu, který je pojmenován **ProjectTaskListEventReceiver**.  
  
6.  Přidejte kód, který `ItemAdded` metoda v **ProjectTaskListEventReceiver** souboru kódu. Úlohy pokaždé, když se přidá novou úlohu, se přidá výchozí datum splatnosti a popis. Výchozí hodnota z důvodu datum je 1. července 2009.  
  
     [!code-vb[SPProjectTaskList#1](../sharepoint/codesnippet/VisualBasic/projecttasklist1/projecttasklisteventreceiver/projecttasklisteventreceiver.vb#1)]
     [!code-csharp[SPProjectTaskList#1](../sharepoint/codesnippet/CSharp/projecttasklist/projecttasklisteventreceiver/projecttasklisteventreceiver.cs#1)]  
  
##  <a name="CustomizeFeature"></a>Přizpůsobení funkcí seznamu úkolů projektu  
 Když vytvoříte řešení služby SharePoint, Visual Studio automaticky vytvoří funkce pro výchozí položky projektu. Nastavení seznamu úkolů projektu pro web služby SharePoint můžete přizpůsobit pomocí návrháře funkce.  
  
#### <a name="to-customize-the-project-task-list-feature"></a>Chcete-li přizpůsobit funkce seznamu úkolů projektu  
  
1.  V **Průzkumníku řešení**, rozbalte položku **funkce**.  
  
2.  Otevřete místní nabídku pro **Feature1**a potom zvolte **Návrhář zobrazení**.  
  
3.  V **název** zadejte **funkce seznamu úkolů projektu**.  
  
4.  V **oboru** vyberte **webové**.  
  
5.  V **vlastnosti** okno, zadejte **1.0.0.0** hodnotu **verze** vlastnost.  
  
##  <a name="CustomizePackage"></a>Přizpůsobení balíčku seznamu úkolů projektu  
 Při vytváření projektu služby SharePoint, Visual Studio automaticky přidá funkce, které obsahují položky projektu výchozí do balíčku. Nastavení seznamu úkolů projektu pro web služby SharePoint můžete přizpůsobit pomocí návrháře balíčků.  
  
#### <a name="to-customize-the-project-task-list-package"></a>Chcete-li přizpůsobit balíček seznamu úkolů projektu  
  
1.  V **SolutionExplorer**, otevřete místní nabídku pro **balíček**a potom zvolte **Návrhář zobrazení**.  
  
2.  V **název** zadejte **ProjectTaskListPackage**.  
  
3.  Vyberte **resetovat Webový Server** zaškrtávací políčko.  
  
##  <a name="BuildTest"></a>Vytváření a testování seznamu úkolů projektu  
 Když spouštíte projekt, otevře se web služby SharePoint. Ručně však přejděte do umístění seznamu úkolů.  
  
#### <a name="to-test-the-project-task-list"></a>K testování seznamu úkolů projektu  
  
1.  Zvolte klávesy F5 k vytváření a nasazování seznamu úkolů projektu.  
  
     Otevře se stránka serveru SharePoint.  
  
2.  Vyberte **Domů** kartě.  
  
3.  V levém bočním panelu, vyberte **seznamu úkolů projektu** odkaz.  
  
     Zobrazí se stránka seznamu úkolů projektu.  
  
4.  V **nástroje seznamu** , zvolte **položky** kartě.  
  
5.  V **položky** skupiny, vyberte **nová položka** tlačítko.  
  
6.  V **název** textové pole, zadejte **Task1**.  
  
7.  Vyberte **Uložit** tlačítko.  
  
     Po aktualizaci lokality **Task1** úkol se zobrazí termínu splnění 7/1/2009.  
  
8.  Zvolte **Task1**.  
  
     Zobrazí se v podrobném zobrazení úlohy a popis zobrazuje "Toto je kritické úlohy."  
  
##  <a name="Deploy"></a>Nasazení seznamu úkolů projektu  
 Po vytvoření a testování seznamu úkolů projektu, abyste ji mohli nasadit na *místní systém* nebo *vzdáleného systému*. Místní systém je do stejného počítače, na kterém vyvinutá řešení, zatímco vzdáleného systému je do jiného počítače.  
  
#### <a name="to-deploy-the-project-task-list-to-the-local-system"></a>K nasazení seznamu úkolů projektu do místního systému  
  
1.  Na panelu nabídek Visual Studio zvolte **sestavení**, **nasadit řešení**.  
  
     Visual Studio recykluje fond aplikací služby IIS, odvolá všechny existující verze řešení, zkopíruje soubor balíčku (WSP) řešení do služby SharePoint a potom aktivuje její funkce. Teď můžete použít řešení ve službě SharePoint. Další informace o postupu konfigurace nasazení najdete v tématu [postupy: Úprava konfigurace nasazení služby SharePoint](../sharepoint/how-to-edit-a-sharepoint-deployment-configuration.md).  
  
#### <a name="to-deploy-the-project-task-list-to-a-remote-system"></a>K nasazení seznamu úkolů projektu do vzdáleného systému  
  
1.  Na panelu nabídek Visual Studio zvolte **sestavení**, **publikovat**.  
  
2.  V **publikovat** dialogovém okně vyberte **publikovat do systému souborů** tlačítko.  
  
     Můžete změnit v cílovém umístění **publikovat** dialogové okno tak, že zvolíte tlačítko se třemi tečkami ![ikonu třemi tečkami](../sharepoint/media/ellipsisicon.gif "ikonu třemi tečkami") a potom přejdete do jiného umístění.  
  
3.  Vyberte **publikovat** tlačítko.  
  
     Soubor WSP se vytvoří pro řešení.  
  
4.  Zkopírujte soubor WSP ke vzdálenému systému SharePoint.  
  
5.  Pomocí prostředí PowerShell `Add-SPUserSolution` příkaz k instalaci balíčku na vzdálenou instalaci služby SharePoint. (Pro řešení ve farmách, použijte `Add-SPSolution` příkaz.)  
  
     Například `Add-SPUserSolution C:\MyProjects\ProjectTaskList\ProjectTaskList\bin\Debug\ProjectTaskList.wsp`.  
  
6.  Pomocí prostředí PowerShell `Install-SPUserSolution` příkaz k nasazení řešení. (Pro řešení ve farmách, použijte `Install-SPSolution` příkaz.)  
  
     Například `Install-SPUserSolution -Identity ProjectTaskList.wsp -Site http://NewSiteName`.  
  
     Další informace o vzdálené nasazení najdete v tématu [pomocí řešení](http://go.microsoft.com/fwlink/?LinkId=217680) a [přidání a nasazení řešení pomocí prostředí PowerShell v produktu SharePoint 2010](http://go.microsoft.com/fwlink/?LinkId=217682).  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o tom, jak přizpůsobit a nasadit řešení služby SharePoint z v následujících tématech:  
  
-   [Návod: Vytvoření sloupce webu, typu obsahu a seznamu pro službu SharePoint](../sharepoint/walkthrough-create-a-site-column-content-type-and-list-for-sharepoint.md)  
  
-   [Postupy: Vytvoření přijímače událostí](../sharepoint/how-to-create-an-event-receiver.md)  
  
-   [Prostředí Windows PowerShell pro SharePoint Server 2010](http://go.microsoft.com/fwlink/?LinkId=217684)  
  
## <a name="see-also"></a>Viz také  
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  