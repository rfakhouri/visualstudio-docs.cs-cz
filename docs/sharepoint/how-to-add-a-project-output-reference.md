---
title: 'Postupy: Přidání odkazu na výstup projektu | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- project output references [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, project output references
- SharePoint development in Visual Studio, advanced packaging tools
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 22b2073e63d2e6551a47469742142821391c86e3
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56619326"
---
# <a name="how-to-add-a-project-output-reference"></a>Postupy: Přidání odkazu na výstup projektu
  Nasazení do služby SharePoint bez Sharepointu sestavení projektu (nebo souborů .xap v projekty technologie Silverlight), přidejte je jako odkazu na výstup projektu.

 Tento proces vytvoří závislost sestavení řešení mezi dva projekty. Projektů v souvislosti s odkazy na výstup projektu jsou sestaveny předtím, než je sestavíte a nasadíte projektu služby SharePoint.

### <a name="to-add-a-project-output-reference"></a>Přidání odkazu na výstup projektu

1.  Načtení řešení, které obsahuje alespoň jeden projekt služby SharePoint a jeden projekt jiný než služby SharePoint.

2.  V **Průzkumníka řešení**, zvolte položku v uzlu projektu služby SharePoint.

3.  V **vlastnosti** okna, vyberte **odkazy na výstup projektu** vlastnost a klikněte na tlačítko se třemi tečkami (![elipsa ASP.NET – Návrhář mobilních řešení](../sharepoint/media/mwellipsis.gif "ASP. Návrhář mobilních NET Elipsa")) vedle sebe tlačítko.

4.  V **odkazy na výstup projektu** dialogového okna zvolte **přidat** tlačítko.

5.  V podokně vlastností klikněte na šipku vedle položky **typ nasazení** vlastnost a pak zvolte příslušnou hodnotu pro položku mimo SharePoint odkazujete, jako například **ElementFile**.

6.  Klikněte na šipku vedle položky **název projektu**, zvolte název položky projektu jiný než služby SharePoint a klikněte na tlačítko **OK** tlačítko.

## <a name="see-also"></a>Viz také:
- [Zadání informací o balení a nasazení v položkách projektu](../sharepoint/providing-packaging-and-deployment-information-in-project-items.md)
- [Postupy: Označení ovládacích prvků jako bezpečných](../sharepoint/how-to-mark-controls-as-safe-controls.md)
- [Zabalení a nasazení řešení služby SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)
