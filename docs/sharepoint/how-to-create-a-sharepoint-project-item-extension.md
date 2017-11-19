---
title: "Postupy: vytváření rozšíření položky projektu služby SharePoint | Microsoft Docs"
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
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
ms.assetid: 163738b9-e25a-49c9-8f33-4b57a2da6b07
caps.latest.revision: "31"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c8e9faaf0b38623347c2b6e8ff7351f625416e82
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-a-sharepoint-project-item-extension"></a>Postupy: Vytváření rozšíření položky projektu SharePoint
  Vytváření rozšíření položky projektu, pokud chcete přidat další funkce položky projektu služby SharePoint, který už je nainstalovaný v sadě Visual Studio. Další informace najdete v tématu [rozšíření položky projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md).  
  
### <a name="to-create-a-project-item-extension"></a>Chcete-li vytvořit rozšíření položky projektu  
  
1.  Vytvoření projektu knihovny tříd.  
  
2.  Přidejte odkazy na následující sestavení:  
  
    -   Microsoft.VisualStudio.SharePoint  
  
    -   System.ComponentModel.Composition  
  
3.  Vytvořte třídu, která implementuje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> rozhraní.  
  
4.  Přidejte do třídy následující atributy:  
  
    -   <xref:System.ComponentModel.Composition.ExportAttribute>. Tento atribut umožňuje sadě Visual Studio zjišťovat a načíst vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> implementace. Předat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> typ do konstruktoru atributu.  
  
    -   <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. V rozšíření položky projektu tento atribut určuje položka projektu, který chcete rozšířit. Identifikátor položky projektu předejte konstruktoru atributu. Seznam identifikátorů položek projektu, které jsou součástí sady Visual Studio najdete v tématu [rozšíření položky projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md).  
  
5.  V implementaci <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> metoda, použijte členy *projectItemType* parametr pro definování chování rozšíření. Tento parametr je <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> objekt, který poskytuje přístup k událostí definovaných v <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFileEvents> rozhraní. Pro přístup k konkrétní instanci typu položky projektu, jsou rozšíření, zpracování <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> událostech, například <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemInitialized>.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak vytvořit jednoduché rozšíření položky projektu přijímač událostí. Pokaždé, když uživatel přidá příjemce událostí položky do projektu služby SharePoint, toto rozšíření zapíše zprávu, která **výstup** okno a **seznam chyb** okno.  
  
 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#1](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/projectitemextension.cs#1)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#1](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/projectitemextension.vb#1)]  
  
 Tento příklad používá zapsat zprávu do projektu služby SharePoint **výstup** okno a **seznam chyb** okno. Další informace najdete v tématu [pomocí projektu služby SharePoint](../sharepoint/using-the-sharepoint-project-service.md).  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Tento příklad vyžaduje odkazy na následující:  
  
-   Microsoft.VisualStudio.SharePoint  
  
-   System.ComponentModel.Composition  
  
## <a name="deploying-the-extension"></a>Nasazení rozšíření  
 Chcete-li nasadit rozšíření, vytvořte [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] balíček rozšíření (VSIX) pro sestavení a všechny další soubory, které chcete distribuovat s rozšířením. Další informace najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření položek projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md)   
 [Návod: Rozšiřování typu položky projektu SharePoint](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)  
  
  