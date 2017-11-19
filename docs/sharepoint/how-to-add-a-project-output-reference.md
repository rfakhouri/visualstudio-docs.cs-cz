---
title: "Postupy: Přidání odkazu na výstup projektu | Microsoft Docs"
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
- project output references [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, project output references
- SharePoint development in Visual Studio, advanced packaging tools
ms.assetid: 9d6bc25e-bf0d-4483-a691-2ad7a796fa80
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: faf46489be0b9a56485fc93c2138a7f6702c4778
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-a-project-output-reference"></a>Postupy: Přidání odkazu na výstup projektu
  Pokud chcete nasadit sestavení projektu jiný než služby SharePoint (nebo souborů .xap v projekty Silverlight) do služby SharePoint, přidejte je jako odkazu na výstup projektu.  
  
 Tento proces vytvoří závislost sestavení řešení mezi dva projekty. Sestavení projektů, které jsou spojené s odkazy na výstup projektu předtím, než je vytvořen a nasazení projektu služby SharePoint.  
  
### <a name="to-add-a-project-output-reference"></a>Přidání odkazu na výstup projektu  
  
1.  Načtěte řešení, které obsahuje alespoň jeden projektu služby SharePoint a jeden jiný než služby SharePoint projektu.  
  
2.  V **Průzkumníku**, vyberte položku v uzlu projektu služby SharePoint.  
  
3.  V **vlastnosti** okně zvolte **odkazy na výstup projektu** vlastnost a klikněte na tlačítko se třemi tečkami (![ASP.NET – Návrhář mobilních řešení elipsy](../sharepoint/media/mwellipsis.gif "ASP. Asp.net – Návrhář mobilních řešení elipsy")) vedle sebe tlačítko.  
  
4.  V **odkazy na výstup projektu** dialogovém okně vyberte **přidat** tlačítko.  
  
5.  V podokně vlastností zvolte na šipku vedle položky **typ nasazení** vlastnost a potom vyberte odpovídající hodnotu pro položku jiný než služby SharePoint, kterou odkazujete, jako například **ElementFile**.  
  
6.  Vyberte šipku vedle **název projektu**, zvolte název položky projektu jiný než služby SharePoint a poté **OK** tlačítko.  
  
## <a name="see-also"></a>Viz také  
 [Poskytnutí balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [Postupy: označení ovládacích prvků jako bezpečných ovládacích prvků](../sharepoint/how-to-mark-controls-as-safe-controls.md)   
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  