---
title: 'Postupy: Začínáme s přizpůsobením pásu karet'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom Ribbon, adding Ribbon to project
- Ribbon [Office development in Visual Studio], adding
- Ribbon [Office development in Visual Studio], customizing
- customizing the Ribbon, adding Ribbon to project
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 14c4ff1e8bf443351f835d74d44b49bbb61e0321
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56640113"
---
# <a name="how-to-get-started-customizing-the-ribbon"></a>Postupy: Začínáme s přizpůsobením pásu karet
  Přizpůsobení pásu karet aplikace Microsoft Office, přidejte **pás karet (vizuální návrhář)** nebo **pásu karet (XML)** položky projektu sady Office.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

### <a name="to-add-a-ribbon-to-a-project"></a>Chcete-li přidat pásu karet do projektu

1. Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.

2. V **přidat novou položku** dialogu **pás karet (vizuální návrhář)** nebo **pásu karet (XML)**. Další informace o těchto šablon naleznete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).

3. V **název** zadejte název položky pásu karet.

    Názvy nesmí obsahovat následující znaky:

   -   Křížek (#)

   -   Procent (%)

   -   Ampersand (&)

   -   Hvězdička (*)

   -   Svislá čára (|)

   -   Zpětné lomítko (\\)

   -   Dvojtečka (:)

   -   Dvojité uvozovky (")

   -   Menší než (\<)

   -   Větší než (>)

   -   Otazník (?)

   -   Vpřed lomítko (/)

   -   Úvodní a koncové mezery ("")

   -   Názvy vyhrazené pro Windows nebo DOS, jako je například ("nul", "aux", "con", "com1", "lpt1" a tak dále)

4. Klikněte na **OK**.

   Položky pásu karet se zobrazí v **Průzkumníka řešení**. Informace o dalších krocích, najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).

## <a name="see-also"></a>Viz také:
- [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)
- [Návrhář pásu karet](../vsto/ribbon-designer.md)
- [Pás karet – XML](../vsto/ribbon-xml.md)
- [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [Návod: Vytvoření vlastní karty pomocí kódu XML pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)
