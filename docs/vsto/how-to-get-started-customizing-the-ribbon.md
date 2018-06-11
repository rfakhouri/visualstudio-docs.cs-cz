---
title: 'Postupy: Začínáme s přizpůsobením pásu karet'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, adding Ribbon to project
- Ribbon [Office development in Visual Studio], adding
- Ribbon [Office development in Visual Studio], customizing
- customizing the Ribbon, adding Ribbon to project
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0ee9866c01031948fc47bbe95bf762c9328b99a8
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35254602"
---
# <a name="how-to-get-started-customizing-the-ribbon"></a>Postupy: Začínáme s přizpůsobením pásu karet
  Chcete-li přizpůsobit na pásu karet z aplikace Microsoft Office, přidejte **pásu karet (vizuálního návrháře)** nebo **pásu karet (XML)** položku do projektu Office.  
  
 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]  
  
### <a name="to-add-a-ribbon-to-a-project"></a>Chcete-li přidat pásu karet do projektu  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
2.  V **přidat novou položku** dialogové okno, vyberte **pásu karet (vizuálního návrháře)** nebo **pásu karet (XML)**. Další informace o těchto šablon najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).  
  
3.  V **název** zadejte název pro položku pásu karet.  
  
     Názvy nesmí obsahovat následující znaky:  
  
    -   Křížku (#)  
  
    -   Procent (%)  
  
    -   Ampersand (&)  
  
    -   Znak hvězdičky (*)  
  
    -   Svislé čáry (|)  
  
    -   Zpětné lomítko (\\)  
  
    -   Dvojtečkou (:)  
  
    -   Dvojité uvozovky (")  
  
    -   Menší než (\<)  
  
    -   Větší než (>)  
  
    -   Otazník (?)  
  
    -   Předat dál lomítko (/)  
  
    -   Počáteční nebo koncové mezery ("")  
  
    -   Názvy vyhrazené pro Windows nebo DOS například ("nul", "aux", "con", "com1", "lpt1" a tak dále)  
  
4.  Click **OK**.  
  
 Položka pásu karet se zobrazí v **Průzkumníku řešení**. Informace o dalších krocích, najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).  
  
## <a name="see-also"></a>Viz také:  
 [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)   
 [Návrhář pásu karet](../vsto/ribbon-designer.md)   
 [Kódu XML pásu karet](../vsto/ribbon-xml.md)   
 [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)   
 [Návod: Vytvoření vlastní karty pomocí kódu XML pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)  
  
  