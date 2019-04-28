---
title: 'Postupy: Vytváření rozšíření položky projektu služby SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- project items [SharePoint development in Visual Studio], extending
- SharePoint project items, extending
- SharePoint development in Visual Studio, extending project items
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: c46b629227b1b3d73ee4bc6a265c867921937df2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62966960"
---
# <a name="how-to-create-a-sharepoint-project-item-extension"></a>Postupy: Vytváření rozšíření položky projektu SharePoint
  Vytváření rozšíření položky projektu, pokud chcete přidat funkce do položky projektu služby SharePoint, která je již nainstalována v sadě Visual Studio. Další informace najdete v tématu [položek projektu služby SharePoint rozšiřte](../sharepoint/extending-sharepoint-project-items.md).

### <a name="to-create-a-project-item-extension"></a>Chcete-li vytvořit rozšíření položky projektu

1. Vytvořte projekt knihovny tříd.

2. Přidejte odkazy na následující sestavení:

    - Microsoft.VisualStudio.SharePoint

    - System.ComponentModel.Composition

3. Vytvořte třídu, která implementuje <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> rozhraní.

4. Přidejte do třídy následující atributy:

    - <xref:System.ComponentModel.Composition.ExportAttribute>. Tento atribut umožňuje sadě Visual Studio zjišťovat a načíst vaše <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> implementace. Předat <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension> typ konstruktoru atributu.

    - <xref:Microsoft.VisualStudio.SharePoint.SharePointProjectItemTypeAttribute>. V rozšíření položky projektu tento atribut určuje položku projektu, kterou chcete rozšířit. Předejte konstruktoru atributu ID položky projektu. Seznam ID položky projektu, které jsou součástí sady Visual Studio najdete v tématu [položek projektu služby SharePoint rozšiřte](../sharepoint/extending-sharepoint-project-items.md).

5. Ve vaší implementaci <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeExtension.Initialize%2A> metody, použijte členy *projectItemType* parametr definuje chování rozšíření. Tento parametr je <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType> objekt, který poskytuje přístup k události definované v <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFileEvents> rozhraní. Přístup ke konkrétní instanci rozšiřování typu položky projektu, zpracování <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents> událostech, například <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemAdded> a <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemEvents.ProjectItemInitialized>.

## <a name="example"></a>Příklad
 Následující příklad kódu ukazuje, jak vytvořit jednoduché rozšíření položky projektu příjemce událostí. Pokaždé, když uživatel přidá položku projektu příjemce událostí do projektu služby SharePoint, toto rozšíření zapíše zprávu do **výstup** okno a **seznam chyb** okna.

 [!code-csharp[SPExtensibility.ProjectSystemExtension.General#1](../sharepoint/codesnippet/CSharp/projectsystemexamples/extension/projectitemextension.cs#1)]
 [!code-vb[SPExtensibility.ProjectSystemExtension.General#1](../sharepoint/codesnippet/VisualBasic/projectsystemexamples/extension/projectitemextension.vb#1)]

 Tento příklad používá k zápisu zprávy do projektu služby SharePoint **výstup** okno a **seznam chyb** okna. Další informace najdete v tématu [použijte službu projektu SharePoint](../sharepoint/using-the-sharepoint-project-service.md).

## <a name="compile-the-code"></a>Kompilace kódu
 Tento příklad vyžaduje odkazy na následující sestavení:

- Microsoft.VisualStudio.SharePoint

- System.ComponentModel.Composition

## <a name="deploy-the-extension"></a>Nasazení rozšíření
 Chcete-li nasadit rozšíření, vytvořte [!include[vsprvs](../sharepoint/includes/vsprvs-md.md)] extension (VSIX) balíčku pro sestavení a všechny další soubory, které chcete distribuovat s příponou. Další informace najdete v tématu [nasazení rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/deploying-extensions-for-the-sharepoint-tools-in-visual-studio.md).

## <a name="see-also"></a>Viz také:
- [Rozšíření položek projektu služby SharePoint](../sharepoint/extending-sharepoint-project-items.md)
- [Návod: Rozšíření typu položky projektu SharePoint](../sharepoint/walkthrough-extending-a-sharepoint-project-item-type.md)
