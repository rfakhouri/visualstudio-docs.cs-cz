---
title: Definování typů položek projektu služby SharePoint vlastní | Dokumentace Microsoftu
ms.date: 02/02/2017
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
ms.openlocfilehash: e4b678d0a4a148bbd8a7414c8a7585b50fbc9c01
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53855163"
---
# <a name="define-custom-sharepoint-project-item-types"></a>Definování vlastních typů položek projektu služby SharePoint
  Pokud chcete vytvořit nový typ položky projektu služby SharePoint, definujte novému typu položky projektu služby SharePoint. Například Visual Studio neobsahuje položky Sharepointového projektu pro přidání polí nebo vlastní akce na Sharepointový Web. Můžete definovat vlastní typy položek Sharepointového projektu pro vytvoření pole, vlastní akce nebo jiné typy součásti služby SharePoint.  
  
## <a name="tasks-for-defining-sharepoint-project-item-types"></a>Úlohy pro definování typů položek projektu služby SharePoint
 K definování typu položky projektu vlastní, vytváření sestavení rozšíření sady Visual Studio, který implementuje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider> rozhraní. Další informace najdete v tématu [jak: Definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).  
  
 Při definování vlastního typu položky projektu, můžete také přidat následující funkce do položky projektu:  
  
- Přidání položky místní nabídky do položky projektu. Položka nabídky se zobrazí, když otevřete místní nabídku pro položku projektu v **Průzkumníka řešení** pravým tlačítkem na položku projektu nebo jej vyberete a potom kliknete **Shift** +  **F10** klíče. Další informace najdete v tématu [jak: Přidání položky místní nabídky do vlastního typu položky projektu SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md).  
  
- Přidání vlastních vlastností do položky projektu. Vlastnost se zobrazí v **vlastnosti** okno při výběru položky projektu v **Průzkumníka řešení**. Další informace najdete v tématu [jak: Přidání vlastnosti do vlastního typu položky projektu SharePoint](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md).  
  
  Pokud chcete povolit ostatním vývojářům použít vaši položku projektu v sadě Visual Studio, vytvořte soubor .spdata a vytvořte šablonu položky nebo šablony projektu, který je přidružený k položce projektu. Další informace najdete v tématu [položky vytvářet šablony a šablony projektů pro položky Sharepointového projektu](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md).  
  
## <a name="understand-the-relationship-between-project-item-types-and-project-item-instances"></a>Porozumět vztahu mezi typů položek projektu a instance položky projektu
 Při definování typu položky projektu služby SharePoint sady Visual Studio načte vaše rozšíření při přidání položky projektu přidruženého typu do projektu služby SharePoint. Například, pokud definujete nový **vlastní akce** typu položky projektu, Visual Studio načte vaše rozšíření, když uživatel přidá **vlastní akce** položku projektu do projektu. Visual Studio používá stejnou instanci rozšíření pro všechny výskyty typ položky přidružený projekt. V předchozím příkladu, pokud uživatel přidá sekundy **vlastní akce** položku projektu do projektu, stejnou instanci rozšíření se používá k úpravě druhé položky projektu.  
  
 Přístup ke konkrétní instanci typu položky projektu, zpracovat jeden z <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> události *projectItemTypeDefinition* parametrů ve vaší implementaci <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeProvider.InitializeType%2A> metody. Například pokud chcete zjistit, při přidání vlastního typu položky projektu do projektu, zpracovat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> událostí. Další informace najdete v tématu [jak: Definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md).  
  
## <a name="see-also"></a>Viz také:
 [Postupy: Definování typu položky projektu SharePoint](../sharepoint/how-to-define-a-sharepoint-project-item-type.md)   
 [Postupy: Přidání vlastnosti do vlastního typu položky projektu SharePoint](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)   
 [Postupy: Přidání položky místní nabídky do vlastního typu položky projektu SharePoint](../sharepoint/how-to-add-a-shortcut-menu-item-to-a-custom-sharepoint-project-item-type.md)   
 [Vytváření šablon položek a projektů pro položky projektu SharePoint](../sharepoint/creating-item-templates-and-project-templates-for-sharepoint-project-items.md)   
 [Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 1](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-1.md)   
 [Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 2](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-2.md)   
 [Návod: Vytvoření položky projektu sloupce webu pomocí šablony projektu, část 2](../sharepoint/walkthrough-creating-a-site-column-project-item-with-a-project-template-part-2.md)   
 [Nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md)  
