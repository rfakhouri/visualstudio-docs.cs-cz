---
title: 'Průvodce: Vytváření DataTable v návrháři datových sad'
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- DataTable objects, creating
- Dataset Designer, creating data tables
- tables [Visual Studio], creating
- data [Visual Studio], Dataset Designer
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 721613b36a14c82c67c4cc187593651a4fd24acd
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54972375"
---
# <a name="walkthrough-create-a-datatable-in-the-dataset-designer"></a>Průvodce: Vytvoření datové tabulky v návrháři datových sad

Tento návod popisuje, jak vytvořit <xref:System.Data.DataTable> (bez objektu TableAdapter) pomocí **Návrhář Dataset**. Informace o vytváření tabulek dat, které obsahují objekty TableAdapter najdete v tématu [vytvoření a konfigurace objektů TableAdapter](../data-tools/create-and-configure-tableadapters.md).

## <a name="create-a-new-windows-forms-application"></a>Vytvoření nové aplikace Windows Forms

1. V sadě Visual Studio na **souboru** nabídce vyberte možnost **nový** > **projektu**.

2. Rozbalte buď **Visual C#** nebo **jazyka Visual Basic** v levém podokně vyberte **Windows Desktop**.

3. V prostředním podokně, vyberte **aplikace Windows Forms** typ projektu.

4. Pojmenujte projekt **DataTableWalkthrough**a klikněte na tlačítko **OK**.

     **DataTableWalkthrough** projekt je vytvořen a přidán do **Průzkumníka řešení**.

## <a name="add-a-new-dataset-to-the-application"></a>Přidat novou datovou sadu do aplikace

1.  Na **projektu** nabídce vyberte možnost **přidat novou položku**.

     Zobrazí se dialogové okno **Přidat novou položku**.

2.  V levém podokně vyberte **Data**a pak vyberte **datovou sadu** v prostředním podokně.

3.  Zvolte **přidat**.

     Visual Studio přidá soubor s názvem **DataSet1.xsd** do projektu a otevře jej v **Návrhář Dataset**.

## <a name="add-a-new-datatable-to-the-dataset"></a>Přidat nové datové tabulky do datové sady

1.  Přetáhněte **DataTable** z **datovou sadu** kartě **nástrojů** na **Návrhář Dataset**.

     Tabulku s názvem **DataTable1** se přidá do datové sady.

2.  Klikněte na záhlaví **DataTable1** a přejmenujte jej `Music`.

## <a name="add-columns-to-the-datatable"></a>Přidání sloupců do DataTable

1.  Klikněte pravým tlačítkem myši **Hudba** tabulky. Přejděte na **přidat**a potom klikněte na tlačítko **sloupec**.

2.  Název sloupce `SongID`.

3.  V **vlastnosti** okno, nastaveno <xref:System.Data.DataColumn.DataType%2A> vlastnost <xref:System.Int16?displayProperty=fullName>.

4.  Tento postup opakujte a přidejte následující sloupce:

     `SongTitle`: <xref:System.String?displayProperty=fullName>

     `Artist`: <xref:System.String?displayProperty=fullName>

     `Genre`: <xref:System.String?displayProperty=fullName>

## <a name="set-the-primary-key-for-the-table"></a>Nastavit primární klíč pro tabulku

Všechny tabulky dat by měl mít primární klíč. Primární klíč jednoznačně identifikuje konkrétní záznam v tabulce dat.

Chcete-li nastavit primární klíč, klikněte pravým tlačítkem **SongID** sloupec a pak klikněte na tlačítko **nastavit primární klíč**. Ikona klíče se zobrazí vedle **SongID** sloupce.

## <a name="save-your-project"></a>Uložit projekt

Chcete-li uložit **DataTableWalkthrough** projektu, na **soubor** nabídce vyberte možnost **Uložit vše**.

## <a name="see-also"></a>Viz také:

- [Vytvoření a konfigurace datových sad v sadě Visual Studio](../data-tools/create-and-configure-datasets-in-visual-studio.md)
- [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)
- [Ověřování dat](../data-tools/validate-data-in-datasets.md)