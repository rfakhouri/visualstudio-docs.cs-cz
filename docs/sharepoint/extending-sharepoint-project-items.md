---
title: Rozšíření položek projektu služby SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 1cc202b2e3e303f8f6e92b82bbfbc6f5525966bf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="extending-sharepoint-project-items"></a>Rozšíření položek projektu služby SharePoint
  Vytváření rozšíření položky projektu, pokud chcete přidat funkce typu položky projektu služby SharePoint, který už je nainstalovaný v sadě Visual Studio. Například můžete vytvořit rozšíření pro integrované **příjemce událostí** nebo **definice seznamu** položky projektu v sadě Visual Studio, nebo můžete vytvořit rozšíření pro vlastního typu položky projektu. Můžete také vytvořit rozšíření pro všechny typy položek projektu služby SharePoint.  
  
## <a name="tasks-for-extending-sharepoint-project-items"></a>Úlohy pro rozšíření položky projektu služby SharePoint  
 Do rozšíření položky projektu, sestavení sestavení rozšíření sady Visual Studio, který implementuje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> rozhraní. Další informace najdete v tématu [postupy: vytváření rozšíření položky projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).  
  
 Když rozšíříte položka projektu, můžete také přidat následující funkce do položky projektu:  
  
-   Přidání položky místní nabídky do položky projektu. Položky nabídky se zobrazí, když otevřete místní nabídku pro položku projektu v **Průzkumníku řešení**. Otevřete kliknutím pravým tlačítkem na projekt položky místní nabídky nebo tak, že ho vyberete a pak vyberete Shift + F10 klíče. Další informace najdete v tématu [postupy: Přidání položky místní nabídky do rozšíření položky projektu služby SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension.md).  
  
-   Přidáte vlastní vlastnost pro položky projektu. Vlastnost se zobrazí v **vlastnosti** okno při výběru položky projektu v **Průzkumníku řešení**. Další informace najdete v tématu [postupy: Přidání vlastnosti do rozšíření položky projektu služby SharePoint](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md).  
  
 Návod, jak vytvořit, nasadit a testování rozšíření položky projektu najdete v tématu [návod: rozšiřování typu položky projektu SharePoint](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md).  
  
## <a name="understanding-the-relationship-between-project-item-extensions-and-project-item-instances"></a>Vztah mezi rozšíření položky projektu a instance položky projektu  
 Při vytváření rozšíření položky projektu sady Visual Studio načte rozšíření, když je položka projektu přidružené typu přidán do projektu služby SharePoint. Například pokud vytvoříte rozšíření pro **příjemce událostí** položky projektu sady Visual Studio načte rozšíření při přidání **příjemce událostí** položka projektu pro projekt. Visual Studio používá stejnou instanci rozšíření pro všechny instance typu položky přidružené projektu. V předchozím příkladu, pokud uživatel přidá druhý **příjemce událostí** položek projektu do projektu, stejnou instanci rozšíření slouží k přizpůsobení druhá položka projektu.  
  
 Přístup ke konkrétní instanci typu položky projektu, jsou rozšíření, zpracovat jeden z <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> události *projectItemType* parametr ve vaší implementace nástroje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> metoda. Například pokud chcete zjistit, když je položka projektu typu rozšiřujete přidat do projektu, zpracování <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> událostí. Další informace najdete v tématu [postupy: vytváření rozšíření položky projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md).  
  
## <a name="identifiers-for-sharepoint-project-items"></a>Identifikátory pro položky projektu služby SharePoint  
 Každé položky projektu služby SharePoint má odpovídající identifikátor řetězce. Identifikátor pro položku projektu musí vědět, pokud chcete provádět následující úlohy:  
  
-   Vytváření rozšíření položky projektu. V takovém případě je nutné předat identifikátor pro položku projektu, který chcete rozšířit do konstruktoru objektu <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. Vytváření rozšíření pro všechny položky typy projektů, předat **\*** hodnota typu řetězec.  
  
-   Položka projektu přidejte do projektu prostřednictvím kódu programu. V takovém případě je nutné předat identifikátor pro položka projektu pro <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemCollection.Add%2A> metoda.  
  
 Následující tabulka uvádí identifikátory pro položky projektu služby SharePoint, které jsou součástí sady Visual Studio.  
  
|Název položky projektu|Identifikátor řetězce|  
|-----------------------|-----------------------|  
|Model katalogu obchodních dat|Microsoft.VisualStudio.SharePoint.BusinessDataConnectivity|  
|Typ obsahu|Microsoft.VisualStudio.SharePoint.ContentType|  
|Příjemce událostí|Microsoft.VisualStudio.SharePoint.EventHandler|  
|Prázdný Element|Microsoft.VisualStudio.SharePoint.GenericElement|  
|Definice seznamu<br /><br /> Definice seznamu z typu obsahu|Microsoft.VisualStudio.SharePoint.ListDefinition|  
|Instance seznamu|Microsoft.VisualStudio.SharePoint.ListInstance|  
|Modul|Microsoft.VisualStudio.SharePoint.Module|  
|Sekvenční pracovní postup<br /><br /> Pracovní postup stavového stroje|Microsoft.VisualStudio.SharePoint.Workflow|  
|Definice webu|Microsoft.VisualStudio.SharePoint.SiteDefinition|  
|Visual webové části|Microsoft.VisualStudio.SharePoint.VisualWebPart|  
|Webová část|Microsoft.VisualStudio.SharePoint.WebPart|  
|Formuláře přidružení pracovního postupu|Microsoft.VisualStudio.SharePoint.WorkflowAssociation|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření rozšíření položky projektu služby SharePoint](../sharepoint/how-to-create-a-sharepoint-project-item-extension.md)   
 [Postupy: Přidání položky místní nabídky do rozšíření položky projektu SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-sharepoint-project-item-extension.md)   
 [Postupy: Přidání vlastnosti do rozšíření položky projektu SharePoint](../sharepoint/how-to-add-a-property-to-a-sharepoint-project-item-extension.md)   
 [Návod: Rozšiřování typu položky projektu SharePoint](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)   
 [Rozšíření systému projektu služby SharePoint](../sharepoint/extending-the-sharepoint-project-system.md)  
  