---
title: 'Postupy: Změna umístění karty na pásu karet'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Ribbon [Office development in Visual Studio], tabs
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a10e7d48bf44305285d13c3b20fa4c1854e2bb59
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54863783"
---
# <a name="how-to-change-the-position-of-a-tab-on-the-ribbon"></a>Postupy: Změna umístění karty na pásu karet
  Můžete změnit pořadí vlastních karet na pásu karet pomocí **kartu Editor kolekce**. Vlastní karty lze umístit před nebo za integrovanou kartu na pásu karet. Vestavěná karta je karta, který je již na pásu karet aplikace Microsoft Office. Například **Data** karta je integrovanou kartou v aplikaci Excel.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-change-the-order-of-tabs-on-the-ribbon"></a>Chcete-li změnit pořadí karet na pásu karet  
  
1.  Vyberte soubor kódu pásu karet (*.vb* nebo *.cs* souborů) v **Průzkumníka řešení**.  
  
2.  Na **zobrazení** nabídky, klikněte na tlačítko **návrháře**.  
  
3.  Klikněte pravým tlačítkem na Návrhář pásu karet a potom klikněte na tlačítko **vlastnosti**.  
  
4.  V **vlastnosti** okna, vyberte **karty** vlastnost a potom klikněte na tlačítko se třemi tečkami (![ASP.NET Mobilní návrháře Elipsa](../sharepoint/media/mwellipsis.gif "technologie ASP.NET Mobile Návrhář Elipsa")).  
  
     **Kartu Editor kolekce** se zobrazí.  
  
5.  V **kartu Editor kolekce**v **členy** seznamu, vyberte kartu, kterou chcete přesunout a klikněte na tlačítko nahoru nebo dolů šipkami, chcete-li změnit pořadí ovládacích prvků.  
  
### <a name="to-position-a-tab-before-or-after-a-built-in-tab-on-the-ribbon"></a>Chcete-li umístit před nebo za integrovanou kartu na pásu karet na kartě  
  
1.  V Návrháři pásu karet vyberte vlastní kartu.  
  
2.  V **vlastnosti** okna, rozbalte **ControlId** vlastnost a ujistěte se, že hodnota **ControlIdType** je nastavena na **vlastní**.  
  
3.  V **vlastnosti** okna, rozbalte **pozice** vlastnost.  
  
4.  Nastavte **PositionType** k odpovídající hodnotě:  
  
    -   **BeforeOfficeId** umístí skupině před zadaným předdefinované karty.  
  
    -   **AfterOfficeId** umístí za integrovanou kartu zadané skupiny.  
  
5.  Nastavte **OfficeId** vlastnosti ID ovládacího prvku předdefinované karty.  
  
     Seznam ID ovládacích prvků naleznete v tématu [soubory nápovědy Office 2010: Office fluent uživatelského rozhraní ovládacího prvku identifikátory](http://go.microsoft.com/fwlink/?LinkID=181052).  
  
## <a name="see-also"></a>Viz také:  
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)   
 [Pás karet – XML](../vsto/ribbon-xml.md)   
 [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Návod: Vytvoření vlastní karty pomocí kódu XML pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
