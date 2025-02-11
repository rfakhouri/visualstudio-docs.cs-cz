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
ms.openlocfilehash: f164a8f1d1c84725530e7a3afab5e63472ae257e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62967895"
---
# <a name="how-to-get-started-customizing-the-ribbon"></a>Postupy: Začínáme s přizpůsobením pásu karet
  Přizpůsobení pásu karet aplikace Microsoft Office, přidejte **pás karet (vizuální návrhář)** nebo **pásu karet (XML)** položky projektu sady Office.

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

### <a name="to-add-a-ribbon-to-a-project"></a>Chcete-li přidat pásu karet do projektu

1. Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.

2. V **přidat novou položku** dialogu **pás karet (vizuální návrhář)** nebo **pásu karet (XML)**. Další informace o těchto šablon naleznete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).

3. V **název** zadejte název položky pásu karet.

    Názvy nesmí obsahovat následující znaky:

   - Křížek (#)

   - Procent (%)

   - Ampersand (&)

   - Hvězdička (*)

   - Svislá čára (|)

   - Zpětné lomítko (\\)

   - Dvojtečka (:)

   - Dvojité uvozovky (")

   - Menší než (\<)

   - Větší než (>)

   - Otazník (?)

   - Vpřed lomítko (/)

   - Úvodní a koncové mezery ("")

   - Názvy vyhrazené pro Windows nebo DOS, jako je například ("nul", "aux", "con", "com1", "lpt1" a tak dále)

4. Klikněte na **OK**.

   Položky pásu karet se zobrazí v **Průzkumníka řešení**. Informace o dalších krocích, najdete v tématu [přehled pásu karet](../vsto/ribbon-overview.md).

## <a name="see-also"></a>Viz také:
- [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)
- [Návrhář pásu karet](../vsto/ribbon-designer.md)
- [Pás karet – XML](../vsto/ribbon-xml.md)
- [Návod: Vytvoření vlastní karty pomocí Návrháře pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [Návod: Vytvoření vlastní karty pomocí kódu XML pásu karet](../vsto/walkthrough-creating-a-custom-tab-by-using-ribbon-xml.md)
