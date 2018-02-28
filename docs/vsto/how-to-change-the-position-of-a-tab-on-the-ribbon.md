---
title: "Postupy: Změna polohy karty na pásu karet | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Ribbon [Office development in Visual Studio], tabs
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- office
ms.openlocfilehash: 5016651a6cc4f1316536c22d555a65aaba64b788
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-change-the-position-of-a-tab-on-the-ribbon"></a>Postupy: Změna polohy karty na pásu karet
  Můžete změnit pořadí vlastní karty na pásu karet pomocí **Karta Editor kolekce**. Vlastní karty můžete umístit před nebo po předdefinované karty na pásu karet. Předdefinované karta je karta, která je již na pásu karet z aplikace Microsoft Office. Například **Data** karta je předdefinované karty v aplikaci Excel.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-change-the-order-of-tabs-on-the-ribbon"></a>Chcete-li změnit pořadí karet na pásu karet  
  
1.  Vyberte soubor kódu pásu karet (soubor vb nebo .cs) v **Průzkumníku řešení**.  
  
2.  Na **zobrazení** nabídky, klikněte na tlačítko **Návrhář**.  
  
3.  Klikněte pravým tlačítkem na Návrháře pásu karet a pak klikněte na **vlastnosti**.  
  
4.  V **vlastnosti** vyberte **karty** vlastnost a potom klikněte na tlačítko se třemi tečkami (![ASP.NET – Návrhář mobilních řešení elipsy](../sharepoint/media/mwellipsis.gif "ASP.NET Mobile Návrhář elipsy")).  
  
     **Karta Editor kolekce** se zobrazí.  
  
5.  V **Karta Editor kolekce**v **členy** seznamu, vyberte kartu chcete přesunout a klikněte na tlačítko nahoru nebo dolů pořadí karet na šipku.  
  
### <a name="to-position-a-tab-before-or-after-a-built-in-tab-on-the-ribbon"></a>Na pozici na kartě před nebo po předdefinované karty na pásu karet  
  
1.  V Návrháři pásu karet vyberte vlastní karty.  
  
2.  V **vlastnosti** okno, rozbalte **ControlId** vlastnost a potom zkontrolujte, zda hodnota **ControlIdType** je nastavena na **vlastní**.  
  
3.  V **vlastnosti** okno, rozbalte **pozice** vlastnost.  
  
4.  Nastavte **PositionType** vlastnost na odpovídající hodnotu:  
  
    -   **BeforeOfficeId** umisťuje skupině před zadaný předdefinované karty.  
  
    -   **AfterOfficeId** umisťuje skupině po zadaný předdefinované karty.  
  
5.  Nastavte **OfficeId** vlastnost ID ovládacího prvku předdefinované karty.  
  
     Seznam ID ovládacích prvků, naleznete v části [soubory nápovědy Office 2010: Office Fluent uživatelské rozhraní ovládacího prvku identifikátory](http://go.microsoft.com/fwlink/?LinkID=181052).  
  
## <a name="see-also"></a>Viz také  
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)   
 [Kódu XML pásu karet](../vsto/ribbon-xml.md)   
 [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Návod: Vytvoření vlastní karty pomocí kódu XML pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  