---
title: Přidružení vlastních dat k SharePoint rozšíření nástrojů | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- projects [SharePoint development in Visual Studio], associating custom data
- project items [SharePoint development in Visual Studio], associating custom data
- SharePoint project items, associating custom data
- SharePoint projects, associating custom data
- SharePoint development in Visual Studio, extensibility features
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: b72e058a2ef025b0118dac8fd419e75d1ad53349
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2018
ms.locfileid: "36327226"
---
# <a name="associate-custom-data-with-sharepoint-tools-extensions"></a>Přidružení vlastních dat k rozšíření nástrojů SharePoint
  Přidáním vlastních dat k určitým objektům v rozšíření nástrojů služby SharePoint. To je užitečné, když se data v jedné části rozšíření, kterou chcete později přístup z jiných kódu ve vašem rozšíření. Místo implementace vlastní způsob, jak ukládat a přistupovat k datům, můžete přidružit objekt data ve vašem rozšíření a následně načíst data ze stejného objektu později.  
  
 Přidání vlastních dat do objektů je také užitečné, pokud chcete zachovat data, která jsou relevantní pro konkrétní položku v sadě Visual Studio. Rozšíření nástrojů služby SharePoint jsou načteny pouze jednou, v sadě Visual Studio, takže toto rozšíření může pracovat s několik různých položek (jako jsou projekty, projektu položek, nebo **Průzkumníka serveru** uzly) kdykoli. Pokud máte vlastní data, která jsou relevantní jenom pro konkrétní položku, můžete přidat data do objektu, který představuje tuto položku.  
  
 Když přidáte vlastní data pro objekty v rozšíření nástrojů služby SharePoint, není zachována data. Data jsou k dispozici pouze během životnost objektu. Jakmile je objekt uvolněn systémem uvolňování paměti, data budou ztracena.  
  
 V rozšíření systému projektu služby SharePoint můžete také uložit řetězec data, která přetrvává i po rozšíření je odpojen. Další informace najdete v tématu [ukládání dat do rozšíření systému projektu služby SharePoint](../sharepoint/saving-data-in-extensions-of-the-sharepoint-project-system.md).  
  
## <a name="objects-that-can-contain-custom-data"></a>Objekty, které mohou obsahovat vlastní data
 U všech objektů v modelu objektu nástroje služby SharePoint, který implementuje můžete přidat vlastní data <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject> rozhraní. Toto rozhraní definuje právě jednu vlastnost, <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A>, což je kolekce vlastních datových objektů. Implementovat následující typy <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject>:  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IMappedFolder>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IMenuItem>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProject>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeature>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectFeatureResourceFile>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItem>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemFile>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemType>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectItemTypeDefinition>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectMember>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.ISharePointProjectPackage>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Deployment.IDeploymentContext>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNode>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeType>  
  
-   <xref:Microsoft.VisualStudio.SharePoint.Explorer.IExplorerNodeTypeDefinition>  
  
## <a name="add-and-retrieve-custom-data"></a>Přidání a načtení vlastních dat
 Přidání vlastních dat k objektu v rozšíření nástrojů služby SharePoint, získat <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> vlastnost v objektu, které chcete přidat data a pak použijte <xref:Microsoft.VisualStudio.SharePoint.IAnnotationDictionary.Add%2A> metoda pro přidání dat do objektu.  
  
 Vlastní data načíst z objektu v rozšíření nástrojů služby SharePoint, získat <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> vlastnost objektu a pak použijte jednu z následujících metod:  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IAnnotationDictionary.TryGetValue%2A>. Tato metoda vrátí hodnotu **true** Pokud datový objekt existuje, nebo **false** Pokud neexistuje. Tuto metodu můžete použít k načtení instancí typy hodnot nebo odkazové typy.  
  
-   <xref:Microsoft.VisualStudio.SharePoint.IAnnotationDictionary.GetValue%2A>. Tato metoda vrátí data o objektu, pokud bude nebo **null** Pokud neexistuje. Tato metoda slouží pouze k načtení instancí odkazové typy.  
  
 Následující příklad kódu určuje, zda na datový objekt je již přidružen položka projektu. Pokud datový objekt již není přidružená k položce projekt, pak kód přidá objekt, který má <xref:Microsoft.VisualStudio.SharePoint.IAnnotatedObject.Annotations%2A> vlastnosti položky projektu. Tady je příklad v rámci většího příkladu najdete v sekci [postupy: Přidání vlastnosti do vlastního typu položky projektu služby SharePoint](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md).  
  
 [!code-vb[SPExtensibility.ProjectItemExtension.MenuAndProperty#13](../sharepoint/codesnippet/VisualBasic/projectitemmenuandproperty/extension/projectitemtypeproperty.vb#13)]
 [!code-csharp[SPExtensibility.ProjectItemExtension.MenuAndProperty#13](../sharepoint/codesnippet/CSharp/projectitemmenuandproperty/extension/projectitemtypeproperty.cs#13)]  
  
## <a name="see-also"></a>Viz také:
 [Programování konceptů a funkcí pro rozšíření nástrojů SharePoint](../sharepoint/programming-concepts-and-features-for-sharepoint-tools-extensions.md)   
 [Návod: Vytvoření vlastní položky projektu akce pomocí šablony položky, část 1](../sharepoint/walkthrough-creating-a-custom-action-project-item-with-an-item-template-part-1.md)   
 [Návod: Rozšíření Průzkumníka serveru pro zobrazení webové části](../sharepoint/walkthrough-extending-server-explorer-to-display-web-parts.md)   
 [Postupy: Přidání vlastnosti do projektů služby SharePoint](../sharepoint/how-to-add-a-property-to-sharepoint-projects.md)   
 [Postupy: Přidání vlastnosti do vlastního typu položky projektu SharePoint](../sharepoint/how-to-add-a-property-to-a-custom-sharepoint-project-item-type.md)
   
 
