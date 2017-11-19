---
title: "Postupy: vytvoření webové části služby SharePoint | Microsoft Docs"
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
- Web Parts [SharePoint development in Visual Studio], adding
- Web Parts [SharePoint development in Visual Studio], creating
ms.assetid: 0d037522-c25e-4c24-93b7-518db0f791b7
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 847124dc9a7e4cd80993df5b50c5d3d3b752f228
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-create-a-sharepoint-web-part"></a>Postupy: Vytvoření webové části služby SharePoint
  Můžete vytvořit a upravit webovou část přidáním **webovou část** položky pro všechny projektu služby SharePoint a poté úpravy souboru kódu pro webovou část nebo pomocí návrháře. Další informace najdete v tématu [postupy: vytvoření webové části služby SharePoint pomocí návrháře](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md).  
  
### <a name="to-create-a-sharepoint-web-part"></a>Vytvoření webové části služby SharePoint  
  
1.  Vytvořte nebo otevřete projekt služby SharePoint.  
  
     Další informace najdete v tématu [projektu služby SharePoint a šablony položek projektu](../sharepoint/sharepoint-project-and-project-item-templates.md).  
  
2.  Vyberte uzel projektu služby SharePoint v **Průzkumníku řešení** a potom zvolte **projektu**, **přidat novou položku**.  
  
3.  V **přidat novou položku** dialogové okno, rozbalte seznam **SharePoint** uzel a potom zvolte **2010** uzlu.  
  
4.  V seznamu šablon služby SharePoint, zvolte **webovou část**.  
  
5.  V **název** pole, zadejte název pro webové části a pak zvolte **přidat** tlačítko.  
  
     Webové části se zobrazí v **Průzkumníku řešení**. Další informace o souborech, které zahrnuje webovou část najdete v tématu [vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md).  
  
6.  V **Průzkumníku**, otevřete soubor kódu pro webovou část, kterou jste právě vytvořili.  
  
     Pokud je například název webové části WebPart1, otevřete soubor WebPart1.vb (pro Visual Basic) nebo WebPart1.cs (pro C#).  
  
7.  V souboru kódu přidejte ovládací prvky do metody <xref:System.Web.UI.Control.CreateChildControls%2A>.  
  
     Příklad, naleznete v části [návod: vytvoření webové části pro službu SharePoint](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md).  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [Postupy: vytvoření webové části služby SharePoint pomocí návrháře](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)   
 [Návod: Vytvoření webové části pro službu SharePoint](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)   
 [Návod: Vytvoření webové části pro službu SharePoint pomocí návrháře](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)  
  
  