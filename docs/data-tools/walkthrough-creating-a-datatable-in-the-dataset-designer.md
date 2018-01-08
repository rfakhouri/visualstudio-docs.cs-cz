---
title: "Návod: Vytváření DataTable v Návrháři Dataset | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataTable objects, creating
- Dataset Designer, creating data tables
- tables [Visual Studio], creating
- data [Visual Studio], Dataset Designer
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 7df2579f5556e0e35b4203c700ca3f96f46a7d2f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-datatable-in-the-dataset-designer"></a>Návod: Vytváření DataTable v Návrháři DataSet

Tento návod popisuje, jak vytvořit <xref:System.Data.DataTable> (bez TableAdapter) pomocí **návrháře Dataset**. Informace o vytváření datových tabulek, které zahrnují TableAdapters najdete v tématu [vytvořit a nakonfigurovat TableAdapters](../data-tools/create-and-configure-tableadapters.md).  

Úkoly v tomto návodu zahrnují:  

-   Vytvoření nového projektu aplikace Windows Forms  

-   Přidání nová datová sada pro aplikaci  

-   Přidání nové tabulky dat k datové sadě  

-   Přidávání sloupců do tabulky dat  

-   Nastavení primární klíč pro tabulku  

## <a name="creating-a-new-windows-forms-application"></a>Vytvoření nové aplikace Windows Forms

### <a name="to-create-a-new-windows-forms-application-project"></a>Chcete-li vytvořit nový projekt aplikace Windows Forms  
  
1. V sadě Visual Studio na **soubor** nabídce vyberte možnost **nový**, **projektu...** .  
  
2. Rozbalte **Visual C#** nebo **jazyka Visual Basic** klikněte v levém podokně, pak vyberte **Windows Classic Desktop**.  

3. V prostředním podokně, vyberte **aplikace pro Windows Forms** typ projektu.  

4. Název projektu **DataTableWalkthrough**a potom zvolte **OK**. 
  
     **DataTableWalkthrough** projekt je vytvořen a přidán do **Průzkumníku řešení**.  

## <a name="adding-a-new-dataset-to-the-application"></a>Přidání nová datová sada pro aplikaci

### <a name="to-add-a-new-dataset-item-to-the-project"></a>Postup přidání nové položky datové sady do projektu  
  
1.  Na **projektu** nabídce vyberte možnost **přidat novou položku...** .  
  
     Zobrazí se dialogové okno Přidat novou položku.  
  
2.  V levém podokně vyberte **Data**, pak vyberte **datovou sadu** v prostředním podokně.  
  
3.  Zvolte **přidat**.  
  
     Visual Studio. přidá do souboru s názvem **DataSet1.xsd** do projektu a otevře ji v **návrháře Dataset**.  

## <a name="adding-a-new-datatable-to-the-dataset"></a>Přidání nové DataTable k datové sadě  

### <a name="to-add-a-new-data-table-to-the-dataset"></a>Chcete-li přidat novou tabulku dat k datové sadě  
  
1.  Přetáhněte **DataTable** z **datovou sadu** kartě **sada nástrojů** na **návrháře Dataset**.  
  
     Tabulka s názvem **DataTable1** se přidá do datové sady.  
   
2.  Klikněte na záhlaví okna **DataTable1** a přejmenujte ji `Music`.  

## <a name="adding-columns-to-the-datatable"></a>Přidávání sloupců do DataTable

### <a name="to-add-columns-to-the-datatable"></a>Přidání sloupců do DataTable  
  
1.  Klikněte pravým tlačítkem myši **Hudba** tabulky. Přejděte na příkaz **přidat**a potom klikněte na **sloupec**.  
  
2.  Název sloupce `SongID`.  
  
3.  V **vlastnosti** nastavte <xref:System.Data.DataColumn.DataType%2A> vlastnost <xref:System.Int16?displayProperty=fullName>.  
  
4.  Tento postup opakujte a přidejte následující sloupce:  
  
     `SongTitle`: <xref:System.String?displayProperty=fullName>  
  
     `Artist`: <xref:System.String?displayProperty=fullName>  
  
     `Genre`: <xref:System.String?displayProperty=fullName>  
  
## <a name="setting-the-primary-key-for-the-table"></a>Nastavení primární klíč pro tabulku

Všechny tabulky dat musí mít primární klíč. Primární klíč jednoznačně identifikuje konkrétní záznam v tabulce data.  
  
### <a name="to-set-the-primary-key-of-the-data-table"></a>Chcete-li nastavit primární klíč tabulky dat
  
-   Klikněte pravým tlačítkem myši **SongID** sloupec a pak klikněte na tlačítko **nastavit primární klíč**.  
  
     Ikona klíče se zobrazí vedle **SongID** sloupce.  
  
## <a name="saving-your-project"></a>Ukládání projektu  
  
### <a name="to-save-the-datatablewalkthrough-project"></a>K uložení projektu DataTableWalkthrough  
  
-   Na **soubor** nabídky, klikněte na tlačítko **Uložit vše**.  

## <a name="see-also"></a>Viz také

[Vytvoření a konfigurace datových sad v sadě Visual Studio](../data-tools/create-and-configure-datasets-in-visual-studio.md)  
[Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)  
[Ověřování dat](../data-tools/validate-data-in-datasets.md)  
[Ukládání dat](../data-tools/saving-data.md)