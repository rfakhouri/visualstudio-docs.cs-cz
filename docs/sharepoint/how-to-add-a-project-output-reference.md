---
title: 'Postupy: Přidání odkazu na výstup projektu | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
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
manager: douge
ms.workload:
- office
ms.openlocfilehash: 97bfe044ef89691afdb1a8e845867ce2e177dbb9
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767959"
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
  
## <a name="see-also"></a>Viz také:
 [Poskytnutí balení a informace o nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)   
 [Postupy: označení ovládacích prvků jako bezpečných ovládacích prvků](../sharepoint/how-to-mark-controls-as-safe-controls.md)   
 [Balení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)  
  
  