---
title: 'Postupy: Přidání metody odstranění | Dokumentace Microsoftu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- BDC [SharePoint development in Visual Studio], deleting data
- Business Data Connectivity service [SharePoint development in Visual Studio], Deleter
- BDC [SharePoint development in Visual Studio], Deleter
- BDC [SharePoint development in Visual Studio], removing data
- BDC [SharePoint development in Visual Studio], deleting entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], deleting entity instances
- Business Data Connectivity service [SharePoint development in Visual Studio], deleting data
- Business Data Connectivity service [SharePoint development in Visual Studio], removing data
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: c9d005ef8bade9f83027c216d875d24aad602449
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63418355"
---
# <a name="how-to-add-a-deleter-method"></a>Postupy: Přidání metody odstranění
  Můžete povolit koncový uživatel odstranit záznam dat z externí seznam na Sharepointovém webu tak, že přidání metody odstranění do modelu. Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).

### <a name="to-create-a-deleter-method"></a>Chcete-li vytvořit metodu Deleter

1. Na **návrháři služby BDC**, zvolit entitu.

2. V panelu nabídky zvolte **zobrazení** > **ostatní Windows** > **podrobnosti metody služby BDC**.

    **Podrobnosti metody služby BDC** otevře se okno. Další informace o tomto okně najdete v tématu [přehled nástrojů pro návrh modelu služby BDC](../sharepoint/bdc-model-design-tools-overview.md).

3. V **přidejte metodu** klikněte na položku **vytvořit metodu Deleter**.

    Visual Studio přidá následující prvky modelu. Tyto prvky se zobrazí v **podrobnosti metody služby BDC** okna.

   - Metodu s názvem **odstranit**.

   - Vstupní parametr metody.

   - Popisovač typu pro parametr.

   - Instance metody k metodě.

     Další informace najdete v tématu [navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md).

4. V **Průzkumníka řešení**, otevřete místní nabídku souboru služby kód, který byl vygenerován pro entitu a pak zvolte **zobrazit kód**.

    Soubor kódu služby entity se otevře v editoru kódu. Další informace o souboru kód služby entity, naleznete v tématu [vytvoření modelu připojení obchodních dat](../sharepoint/creating-a-business-data-connectivity-model.md).

5. Přidejte kód do metody odstranění, které chcete odstranit záznam. Následující příklad odstraní řádek z prodejní objednávky pomocí ukázkovou databází AdventureWorks pro SQL Server.

   > [!NOTE]
   > Tento příklad používá dva vstupní parametry.

   > [!NOTE]
   > Nahraďte hodnotu `ServerName` pole s názvem vašeho serveru.

    [!code-csharp[SP_BDC#6](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/salesorderdetailservice.cs#6)]
    [!code-vb[SP_BDC#6](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/salesorderdetailservice.vb#6)]

## <a name="see-also"></a>Viz také:
- [Navrhování modelu připojení obchodních dat](../sharepoint/designing-a-business-data-connectivity-model.md)
- [Postupy: Přidání vyhledávací metody](../sharepoint/how-to-add-a-finder-method.md)
- [Postupy: Přidání konkrétní vyhledávací metody](../sharepoint/how-to-add-a-specific-finder-method.md)
- [Postupy: Přidání metody vytvoření](../sharepoint/how-to-add-a-creator-method.md)
- [Postupy: Přidání aktualizační metody](../sharepoint/how-to-add-an-updater-method.md)
- [Přehled nástroje pro navrhování modelů služby BDC](../sharepoint/bdc-model-design-tools-overview.md)
- [Postupy: Přidání parametru k metodě](../sharepoint/how-to-add-a-parameter-to-a-method.md)
- [Postupy: Definování instance metody](../sharepoint/how-to-define-a-method-instance.md)
