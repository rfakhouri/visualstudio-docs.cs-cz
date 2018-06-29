---
title: 'Návod: Vytváření DataTable v Návrháři DataSet'
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- DataTable objects, creating
- Dataset Designer, creating data tables
- tables [Visual Studio], creating
- data [Visual Studio], Dataset Designer
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 2e02f01924d5bae2770c579c4bfadd314e03cbe3
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089102"
---
# <a name="walkthrough-create-a-datatable-in-the-dataset-designer"></a>Návod: Vytváření DataTable v Návrháři Dataset

Tento návod popisuje, jak vytvořit <xref:System.Data.DataTable> (bez TableAdapter) pomocí **návrháře Dataset**. Informace o vytváření datových tabulek, které zahrnují TableAdapters najdete v tématu [vytvořit a nakonfigurovat TableAdapters](../data-tools/create-and-configure-tableadapters.md).

## <a name="create-a-new-windows-forms-application"></a>Vytvořte novou aplikaci Windows Forms

1. V sadě Visual Studio na **soubor** nabídce vyberte možnost **nový** > **projektu**.

2. Rozbalte **Visual C#** nebo **jazyka Visual Basic** klikněte v levém podokně, pak vyberte **Windows Desktop**.

3. V prostředním podokně, vyberte **aplikace pro Windows Forms** typ projektu.

4. Název projektu **DataTableWalkthrough**a potom zvolte **OK**.

     **DataTableWalkthrough** je vytvořen a přidán do projektu **Průzkumníku řešení**.

## <a name="add-a-new-dataset-to-the-application"></a>Přidat novou datovou sadu pro aplikaci

1.  Na **projektu** nabídce vyberte možnost **přidat novou položku**.

     Zobrazí se dialogové okno Přidat novou položku.

2.  V levém podokně vyberte **Data**, pak vyberte **datovou sadu** v prostředním podokně.

3.  Zvolte **přidat**.

     Visual Studio. přidá do souboru s názvem **DataSet1.xsd** do projektu a otevře ji v **návrháře Dataset**.

## <a name="add-a-new-datatable-to-the-dataset"></a>Přidejte nový element DataTable k datové sadě

1.  Přetáhněte **DataTable** z **datovou sadu** kartě **sada nástrojů** na **návrháře Dataset**.

     Tabulka s názvem **DataTable1** se přidá do datové sady.

2.  Klikněte na záhlaví okna **DataTable1** a přejmenujte ji `Music`.

## <a name="add-columns-to-the-datatable"></a>Přidávání sloupců do DataTable

1.  Klikněte pravým tlačítkem myši **Hudba** tabulky. Přejděte na příkaz **přidat**a potom klikněte na **sloupec**.

2.  Název sloupce `SongID`.

3.  V **vlastnosti** nastavte <xref:System.Data.DataColumn.DataType%2A> vlastnost <xref:System.Int16?displayProperty=fullName>.

4.  Tento postup opakujte a přidejte následující sloupce:

     `SongTitle`: <xref:System.String?displayProperty=fullName>

     `Artist`: <xref:System.String?displayProperty=fullName>

     `Genre`: <xref:System.String?displayProperty=fullName>

## <a name="set-the-primary-key-for-the-table"></a>Nastavit primární klíč pro tabulku

Všechny tabulky dat musí mít primární klíč. Primární klíč jednoznačně identifikuje konkrétní záznam v tabulce data.

Pokud chcete nastavit primární klíč, klikněte pravým tlačítkem myši **SongID** sloupec a potom klikněte na **nastavit primární klíč**. Ikona klíče se zobrazí vedle **SongID** sloupce.

## <a name="save-your-project"></a>Uložení projektu

Uložte projekt DataTableWalkthrough na **soubor** nabídce vyberte možnost **Uložit vše**.

## <a name="see-also"></a>Viz také:

- [Vytvoření a konfigurace datových sad v sadě Visual Studio](../data-tools/create-and-configure-datasets-in-visual-studio.md)
- [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)
- [Ověřování dat](../data-tools/validate-data-in-datasets.md)