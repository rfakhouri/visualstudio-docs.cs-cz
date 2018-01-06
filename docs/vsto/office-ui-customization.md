---
title: "Přizpůsobení uživatelského rozhraní Office | Microsoft Docs"
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
helpviewer_keywords:
- menus [Office development in Visual Studio], customizing
- actions panes [Office development in Visual Studio], creating
- WPF [Office development in Visual Studio]
- toolbars [Office development in Visual Studio], customizing
- Office applications [Office development in Visual Studio], UI customization
ms.assetid: 3d7c7b88-2053-4ada-bfe7-e7bb202c430b
caps.latest.revision: "74"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: c169edc949f195d416194ae3c3ee1111977f649b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="office-ui-customization"></a>Přizpůsobení uživatelského rozhraní systému Office
  Uživatelské rozhraní (UI) můžete přizpůsobit z aplikace Microsoft Office pomocí doplňku Office developer tools v sadě Visual Studio. Toto téma popisuje funkce uživatelského rozhraní, které můžete přizpůsobit v následujících částech:  
  
-   [Porovnání funkcí uživatelského rozhraní](#Comparison)  
  
-   [Podokna akcí a vlastních podoken úloh](#Actions)  
  
-   [Vlastní pás karet uživatelského rozhraní](#Ribbon)  
  
-   [Zobrazení Backstage](#Backstage)  
  
-   [Oblastí formulářů aplikace Outlook](#FormRegion)  
  
-   [Ovládací prvky v dokumentech](#Controls)  
  
-   [Místní nabídky](#Shortcut)  
  
##  <a name="Comparison"></a>Porovnání funkcí uživatelského rozhraní  
 Následující tabulka porovnává hlavní funkce uživatelského rozhraní, které můžete přizpůsobit v projektech Microsoft Office.  
  
|Funkce|Typy podporované projektů|Podporované aplikace Microsoft Office|  
|-------------|-----------------------------|---------------------------------------------|  
|Podokna akcí|Přizpůsobení na úrovni dokumentu|Excel<br /><br /> Word|  
|Vlastní podokna úloh|Doplňků VSTO|Excel<br /><br /> [!INCLUDE[InfoPath_15_short](../vsto/includes/infopath-15-short-md.md)]<br /><br /> [!INCLUDE[InfoPath_14_short](../vsto/includes/infopath-14-short-md.md)]<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Word<br /><br /> Excel|  
|Vlastní pás karet uživatelského rozhraní|Přizpůsobení na úrovni dokumentu<br /><br /> Doplňků VSTO|Excel<br /><br /> [!INCLUDE[InfoPath_15_short](../vsto/includes/infopath-15-short-md.md)]<br /><br /> [!INCLUDE[InfoPath_14_short](../vsto/includes/infopath-14-short-md.md)]<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Projekt<br /><br /> Word<br /><br /> Visio|  
|Zobrazení Backstage|Přizpůsobení na úrovni dokumentu<br /><br /> Doplňků VSTO|Excel<br /><br /> [!INCLUDE[InfoPath_15_short](../vsto/includes/infopath-15-short-md.md)].<br /><br /> [!INCLUDE[InfoPath_14_short](../vsto/includes/infopath-14-short-md.md)]<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Projekt<br /><br /> Word<br /><br /> Visio|  
|Oblastí formulářů aplikace Outlook|Doplňků VSTO|Outlook|  
|Ovládací prvky v dokumentech|Přizpůsobení na úrovni dokumentu<br /><br /> Doplňků VSTO|Excel<br /><br /> Word|  
|Místní nabídky|Přizpůsobení na úrovni dokumentu<br /><br /> Doplňků VSTO|Excel<br /><br /> [!INCLUDE[InfoPath_15_short](../vsto/includes/infopath-15-short-md.md)]<br /><br /> [!INCLUDE[InfoPath_14_short](../vsto/includes/infopath-14-short-md.md)]<br /><br /> Outlook<br /><br /> PowerPoint<br /><br /> Projekt<br /><br /> Word<br /><br /> Visio<br /><br /> Excel|  
  
##  <a name="Actions"></a>Podokna akcí a vlastních podoken úloh  
 Podokna úloh jsou panely uživatelského rozhraní, které jsou obvykle ukotven na jedné straně okna v aplikaci Microsoft Office. Téměř všechny aplikace Microsoft Office zahrnují podokna integrovanou úlohu. Příkladem podokna úloh je v podokně úloh nápovědy v aplikaci Word.  
  
 Nástroje pro vývoj pro Office v sadě Visual Studio poskytují dvěma různými způsoby, chcete-li přizpůsobit podokna úloh:  
  
-   Podokna akcí můžete přidat k přizpůsobení na úrovni dokumentu. Ve výchozím nastavení zobrazí se v podokně Akce na pravé straně aplikace napravo od dokumentu. Na levé straně, horní nebo dolní části dokumentu však lze také zobrazit v podokně Akce.  
  
-   Přidáním vlastního podokna úloh do doplňku VSTO. Uživatele můžete ukotvit vlastních podoken úloh různých stranách okna aplikace, nebo se můžete přetáhnout vlastní podokna úloh do libovolného umístění, v okně.  
  
 Podokna akcí a vlastních podoken úloh poskytují funkce hostováním různých ovládacích prvků, aby pomáhal uživatelům se úlohy, jako je vstupní data. Ve srovnání s skupiny pásu karet, podokna akcí a vlastních podoken úloh poskytují mnohem větší oblasti zahrnuje text a ovládací prvky.  
  
 Další informace o podoknech akcí najdete v tématu [přehled podokna akcí](../vsto/actions-pane-overview.md). Další informace o vlastních podoknech úloh najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).  
  
##  <a name="Ribbon"></a>Vlastní pás karet uživatelského rozhraní  
 Můžete přizpůsobit uživatelské rozhraní pásu karet vystavit funkcionalitu, která přidáte do aplikací v sadě Office. Na pásu karet je způsob, jak uspořádat související příkazy (ve formě ovládací prvky), aby byly snadněji najít. Můžete vytvořit vlastní karty pásu karet a skupiny, které chcete uživatelům umožnit přístup k funkce, které zadáte v řešení. Většina funkcí, které byly zpřístupněny pomocí nabídek a panelů nástrojů v dřívějších verzích systému Microsoft Office je nyní přístupná pomocí pásu karet.  
  
 Další informace najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).  
  
##  <a name="Backstage"></a>Zobrazení Backstage  
 V aplikacích Office, kliknutím **souboru** kartě otevře zobrazení Backstage. Zobrazení Backstage poskytuje uživatelské rozhraní, které kombinuje úlohy na úrovni souborů a akce a nahradí podobné funkce z aplikace Microsoft Office tlačítko k dispozici v systému Microsoft Office 2007. Zobrazení Backstage je plná rozšiřitelnost pomocí XML.  
  
 Visual Studio neposkytuje designer nebo rozhraní API pro přizpůsobení zobrazení Backstage. Ale pokud přidáte **pásu karet (XML)** položku do projektu Office, můžete přidat XML do souboru XML pásu karet pro přizpůsobení zobrazení Backstage. Další informace o **pásu karet (XML)** položek, najdete v části [XML karet](../vsto/ribbon-xml.md).  
  
 Další informace o přizpůsobení zobrazení Backstage najdete v tématu [Úvod do zobrazení Backstage Office 2010 pro vývojáře](http://go.microsoft.com/fwlink/?LinkId=182189) a [přizpůsobení zobrazení Backstage Office 2010 pro vývojáře](http://go.microsoft.com/fwlink/?LinkId=182188).  
  
##  <a name="FormRegion"></a>Oblastí formulářů aplikace Outlook  
 Oblasti formuláře použijte k přidání vlastních funkcí k standardní formuláře aplikace Microsoft Office Outlook. Můžete vytvořit oblasti formuláře, které rozšiřují všechny existující formulář s další pole nebo ovládací prvky. Pokud vytvoříte nové oblasti formuláře pomocí nástrojů pro vývoj pro Office v sadě Visual Studio, můžete použít pouze ovládací prvky Windows Forms v oblasti formuláře. Pokud importujete oblasti formuláře, který byl navržen v aplikaci Outlook, můžete použít jenom nativní aplikaci Outlook ovládací prvky.  
  
 Můžete vytvořit oblasti formuláře, které zabírají různé oblasti uživatelského rozhraní aplikace Outlook. Například sousedících oblasti formuláře se zobrazí v dolní části formuláře na první stránku a každý sousedících oblasti formuláře je sbalitelné. Můžete také přidat oblasti samostatné formuláře, který se zobrazí na stránce úplné další formuláře a poté můžete zobrazit na všechny existující standardní formuláře nebo vlastního formuláře.  
  
 Další informace najdete v tématu [vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md).  
  
##  <a name="Controls"></a>Ovládací prvky v dokumentech  
 Můžete přidat řadu ovládacích prvků do dokumentů aplikace Word a listy aplikace Excel. Například můžete přidat ovládací prvek pro výběr data do dokumentu, aby uživatel můžete zadat data ve standardním formátu, nebo umístit tlačítka na list k odesílání dat do databáze.  
  
 Při vývoji projekty na úrovni dokumentu pro Excel nebo Word, návrháři Visual Studio můžete použít k přidání ovládacích prvků do dokumentu nebo sešitu v projektu v době návrhu, nebo můžete programově přidání ovládacích prvků za běhu. Při vývoji projekty doplňku VSTO pro Excel nebo Word, můžete programově přidání ovládacích prvků do všechny otevřené dokumenty a sešitu v době běhu.  
  
 Další informace najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md) a [ovládacích prvků Windows Forms na přehled dokumenty Office](../vsto/windows-forms-controls-on-office-documents-overview.md).  
  
##  <a name="Shortcut"></a>Místní nabídky  
 Místní nabídky se zobrazí, když kliknete pravým tlačítkem na dokument nebo okna aplikace. Můžete nastavit místní nabídky se objeví po provedení událost, například když uživatel klikne pravým tlačítkem myši dokument, sešit nebo hostitelského ovládacího prvku. Počet příkazy nabídky jinou nebo ovládací prvky můžete přidat do místní nabídky. Vytvořte místní nabídky pomocí XML. Pokud přidáte **pásu karet (XML)** položku do projektu Office, můžete přidat XML do souboru XML pásu karet k vytvoření místní nabídky. Další informace o používání XML při vytváření místních nabídek najdete v tématu [postupy: Přidání příkazů do místních nabídek](../vsto/how-to-add-commands-to-shortcut-menus.md).  
  
## <a name="see-also"></a>Viz také  
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Windows Forms – ovládací prvky na přehled dokumenty sady Office](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Přehled podokna akcí](../vsto/actions-pane-overview.md)   
 [Vytváření oblastí formulářů aplikace Outlook](../vsto/creating-outlook-form-regions.md)   
 [Vlastní podokna úloh](../vsto/custom-task-panes.md)   
 [Použití ovládacích prvků grafického subsystému WPF v řešeních pro systém Office](../vsto/using-wpf-controls-in-office-solutions.md)   
 [Postupy: zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)   
 [Postupy: Zobrazit chyby doplňku uživatelského rozhraní](../vsto/how-to-show-add-in-user-interface-errors.md)   
 [Návod: Shromažďování dat pomocí formuláře Windows](../vsto/walkthrough-collecting-data-using-a-windows-form.md)  
  
  