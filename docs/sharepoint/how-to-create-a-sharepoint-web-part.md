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
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 27826859d2bac9b247132e7fcb2c3721b6d38092
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
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
  
  