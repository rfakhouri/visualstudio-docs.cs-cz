---
title: 'Postupy: Vytvoření webové části SharePoint | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Web Parts [SharePoint development in Visual Studio], adding
- Web Parts [SharePoint development in Visual Studio], creating
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b66cd0b380612502bb982efd464607a4759f9c4b
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54870789"
---
# <a name="how-to-create-a-sharepoint-web-part"></a>Postupy: Vytvoření webové části služby SharePoint
  Můžete vytvořit a přizpůsobit webovou část přidáním **webové části** položky do jakéhokoli projektu SharePoint a poté úpravou souboru kódu webové části nebo s použitím návrháře. Další informace najdete v tématu [jak: Vytvoření webové části služby SharePoint pomocí návrháře](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md).  
  
### <a name="to-create-a-sharepoint-web-part"></a>Vytvoření webové části služby SharePoint
  
1.  Vytvořte nebo otevřete projekt služby SharePoint.  
  
     Další informace najdete v tématu [SharePoint šablony položek projektu a projekt](../sharepoint/sharepoint-project-and-project-item-templates.md).  
  
2.  Zvolte uzel projektu služby SharePoint v **Průzkumníka řešení** a klikněte na tlačítko **projektu** > **přidat novou položku**.  
  
3.  V **přidat novou položku** dialogového okna rozbalte **SharePoint** uzel a klikněte na tlačítko **2010** uzlu.  
  
4.  V seznamu šablon služby SharePoint, zvolte **webové části**.  
  
5.  V **název** pole, zadejte název webové části a klikněte na tlačítko **přidat** tlačítko.  
  
     Webová část se zobrazí v **Průzkumníka řešení**. Další informace o souborech, které obsahuje webovou část, naleznete v tématu [vytvořit webové části pro SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md).  
  
6.  V **Průzkumníka řešení**, otevřete soubor kódu pro webovou část, kterou jste právě vytvořili.  
  
     Například, pokud je název webové části *WebPart1*, otevřete *WebPart1.vb* (v jazyce Visual Basic) nebo *WebPart1.cs* (v C#).  
  
7.  V souboru kódu přidejte ovládací prvky do metody <xref:System.Web.UI.Control.CreateChildControls%2A>.  
  
     Příklad najdete v tématu [názorný postup: Vytvoření webové části pro SharePoint](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md).  
  
## <a name="see-also"></a>Viz také:
 [Vytvoření webové části pro SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [Postupy: Vytvoření webové části služby SharePoint pomocí návrháře](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)   
 [Návod: Vytvoření webové části pro SharePoint](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)   
 [Návod: Vytvoření webové části pro službu SharePoint pomocí návrháře](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)  
