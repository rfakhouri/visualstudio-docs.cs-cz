---
title: 'Postupy: Přidání metody vytvoření | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], Creator
- BDC [SharePoint development in Visual Studio], adding entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], adding entity instances
- BDC [SharePoint development in Visual Studio], adding entities
- Business Data Connectivity service [SharePoint development in Visual Studio], Creator
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 38312384c3e6ce51aa1b5b0b16df378286fc58b0
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63443581"
---
# <a name="how-to-add-a-creator-method"></a>Postupy: Přidání metody vytvoření
  Metody vytvoření zdroje dat entity přidá nová data. Služba obchodní Data připojení (BDC) volá tuto metodu, když se uživatelé rozhodnou **nová položka** tlačítko **pásu karet** seznamu, který je založen na modelu. Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).

### <a name="to-add-a-creator-method"></a>Přidání metody vytvoření

1. Na **návrháři služby BDC**, zvolit entitu.

2. V panelu nabídky zvolte **zobrazení** > **ostatní Windows** >**podrobnosti metody služby BDC**.

    **Podrobnosti metody služby BDC** otevře se okno. Další informace o tomto okně najdete v tématu [přehled nástrojů pro návrh modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md).

3. V **přidejte metodu** klikněte na položku **vytvořit metodu Creator**.

    Visual Studio přidá následující prvky modelu, a tyto prvky se zobrazí v **podrobnosti metody služby BDC** okna.

   - Metodu s názvem **vytvořit**.

   - Vstupní parametr metody.

   - Návratový parametr metody.

   - Typ popisovače parametru.

   - Instance metody k metodě.

     Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).

4. V **Průzkumníka řešení**, otevřete místní nabídku souboru služby kód, který byl vygenerován pro entitu a pak zvolte **zobrazit kód**.

    Soubor kódu služby entity se otevře v editoru kódu. Další informace o souboru kód služby entity, naleznete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).

5. Přidejte kód do metody tvůrce, který přidá data do zdroje dat. Následující příklad přidá kontaktu k ukázkové databázi AdventureWorks pro SQL Server.

   > [!NOTE]
   > Nahraďte hodnotu `ServerName` pole s názvem vašeho serveru.

    [!code-csharp[SP_BDC#4](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#4)]
    [!code-vb[SP_BDC#4](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#4)]

## <a name="see-also"></a>Viz také:
- [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)
- [Postupy: Přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)
- [Postupy: Přidání konkrétní vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)
- [Postupy: Přidání metody odstranění](../sharepoint/how-to-add-a-deleter-method.md)
- [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)
- [Přehled nástroje pro navrhování modelů služby BDC](../sharepoint/bdc-model-design-tools-overview.md)
- [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [Postupy: Definování instance metody](../sharepoint/how-to-define-a-method-instance.md)
