---
title: Definování typů položek projektu služby SharePoint vlastní | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint project items, defining your own types
- project items [SharePoint development in Visual Studio], defining your own types
- SharePoint development in Visual Studio, defining new project item types
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 180d7e4878ca0c9493c949eac055713212c964de
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2018
ms.locfileid: "36326163"
---
# <a name="define-custom-sharepoint-project-item-types"></a>Definování vlastních typů položek projektu služby SharePoint
  Pokud chcete vytvořit nový druh položky projektu služby SharePoint, definujte nového typu položky projektu služby SharePoint. Visual Studio například nezahrnuje položky projektu služby SharePoint pro přidání polí nebo vlastní akce na web služby SharePoint. Můžete definovat vlastních typů položek projektu služby SharePoint pro vytvoření pole, vlastní akce nebo jiné typy součásti služby SharePoint.  
  
## <a name="tasks-for-defining-sharepoint-project-item-types"></a>Úlohy pro definování typů položek projektu služby SharePoint
 K definování typu položky projektu vlastní, sestavení sestavení rozšíření sady Visual Studio, který implementuje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> rozhraní. Další informace najdete v tématu [postupy: definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).  
  
 Při definování typu položky projektu vlastní, můžete také přidat následující funkce do položky projektu:  
  
-   Přidání položky místní nabídky do položky projektu. Položky nabídky se zobrazí, když otevřete místní nabídku pro položku projektu v **Průzkumníku řešení** kliknutím pravým tlačítkem na položku projektu nebo tak, že ho vyberete a pak vyberete **Shift** +  **F10** klíče. Další informace najdete v tématu [postupy: Přidání položky místní nabídky do vlastního typu položky projektu služby SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md).  
  
-   Přidáte vlastní vlastnost pro položky projektu. Vlastnost se zobrazí v **vlastnosti** okno při výběru položky projektu v **Průzkumníku řešení**. Další informace najdete v tématu [postupy: Přidání vlastnosti do vlastního typu položky projektu služby SharePoint](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md).  
  
 Pokud chcete povolit jiné vývojářům používat vaše položky projektu v sadě Visual Studio, vytvořte soubor .spdata a vytvoření šablony položky nebo šablona projektu, která je přidružená k položce projektu. Další informace najdete v tématu [položky vytvářet šablony a šablony projektů pro položky projektu služby SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
## <a name="understand-the-relationship-between-project-item-types-and-project-item-instances"></a>Pochopení vztah mezi typů položek projektu a instancí položky projektu
 Při definování typu položky projektu služby SharePoint, načte Visual Studio rozšíření, když je položka projektu přidružené typu přidán do projektu služby SharePoint. Například, pokud je definovat novou **vlastní akce** typu položky projektu, Visual Studio načte rozšíření, pokud uživatel přidá **vlastní akce** položka projektu pro projekt. Visual Studio používá stejnou instanci rozšíření pro všechny instance typu položky přidružené projektu. V předchozím příkladu, pokud uživatel přidá druhý **vlastní akce** položek projektu do projektu, stejnou instanci rozšíření slouží k přizpůsobení druhá položka projektu.  
  
 Přístup ke konkrétní instanci typu položky projektu, zpracovat jeden z <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> události *projectItemTypeDefinition* parametr ve vaší implementace nástroje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> metoda. Například pokud chcete zjistit, po přidání vlastního typu položky projektu do projektu, zpracování <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> událostí. Další informace najdete v tématu [postupy: definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).  
  
## <a name="see-also"></a>Viz také:
 [Postupy: definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [Postupy: Přidání vlastnosti do vlastního typu položky projektu SharePoint](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [Postupy: Přidání položky místní nabídky do vlastního typu položky projektu SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)   
 [Vytváření šablon položek a šablony projektů pro položky projektu SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)   
 [Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 2](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)   
 [Nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
  
