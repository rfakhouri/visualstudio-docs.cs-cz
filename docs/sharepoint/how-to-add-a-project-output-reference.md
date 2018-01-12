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
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 0114971baa164858add68f2f1d6f571407ba5320
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
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
  
  