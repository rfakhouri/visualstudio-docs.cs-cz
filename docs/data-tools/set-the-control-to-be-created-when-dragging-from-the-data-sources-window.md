---
title: Nastavení ovládacího prvku k vytvoření při přetažení z okna zdroje dat
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Data Sources Window, select controls
- Windows Forms, displaying data
- data [Visual Studio], displaying on Windows Forms
- data [Visual Studio], Data Sources window
ms.assetid: 20597ff8-0c98-43ec-8fb1-05376804ba48
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 442a98b76efb8013d5d40607e14586299718afc3
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2019
ms.locfileid: "66715091"
---
# <a name="set-the-control-to-be-created-when-dragging-from-the-data-sources-window"></a>Nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdrojů dat

Můžete vytvořit ovládací prvky vázané na data přetažením položek z **zdroje dat** okna do Návrháře WPF nebo Návrhář formulářů Windows. Každá položka v **zdroje dat** okno má výchozí ovládací prvek, který je vytvořen při přetažení do návrháře. Můžete však vytvořit jiného ovládacího prvku.

## <a name="set-the-controls-to-be-created-for-data-tables-or-objects"></a>Nastavte ovládací prvky mají být vytvořeny pro tabulky dat nebo objekty

Před přetažením položky, které představují tabulky dat nebo objekty z **zdroje dat** okna, můžete použít k zobrazení všech dat v jednom ovládacím prvku nebo v samostatném ovládacím prvku zobrazit každý sloupec nebo vlastnost.

V tomto kontextu termín *objekt* odkazuje na vlastní obchodní objekt, entity (v Entity Data Model) nebo objekt vrácený službou.

### <a name="to-set-the-controls-to-be-created-for-data-tables-or-objects"></a>Chcete-li nastavit ovládací prvky mají být vytvořeny pro tabulky dat nebo objekty

1. Ujistěte se, **WPF** Návrhář nebo **Windows Forms** je otevřený Návrhář.

2. V **zdroje dat** okna, vyberte položku, která představuje data tabulky nebo objektu, který chcete nastavit.

   > [!TIP]
   > Pokud **zdroje dat** není otevřené okno, otevřete ho tak, že vyberete **zobrazení** > **ostatní Windows** > **zdroje dat**.

3. Klikněte na rozevírací nabídku pro položku a pak klikněte na jednu z následujících možností v nabídce:

    - Chcete-li zobrazit každé datové pole v samostatném ovládacím prvku, klikněte na tlačítko **podrobnosti**. Při přetažení položky dat do návrháře, tato akce vytvoří jiný ovládací prvek vázaný na data pro každý sloupec nebo vlastnost nadřazené tabulky dat nebo objekt, spolu s popisky pro každý ovládací prvek.

    - K zobrazení všech dat v ovládacím prvku jednoho, vyberte jiný ovládací prvek v seznamu, jako je například **DataGrid** nebo **seznamu** v aplikaci WPF nebo **DataGridView** ve Windows Forms aplikace.

    Seznam dostupných ovládacích prvků, závisí na návrháře, který máte otevřený, kterou verzi rozhraní .NET váš projekt cílí, a určuje, zda jste přidali vlastní ovládací prvky tuto podporu datové vazby k **nástrojů**. Pokud ovládací prvek, který chcete vytvořit není v seznamu dostupných ovládacích prvků, můžete přidat ovládací prvek do seznamu. Další informace najdete v tématu [přidání vlastních ovládacích prvků do okna zdroje dat](../data-tools/add-custom-controls-to-the-data-sources-window.md).

    Další informace o vytvoření vlastního ovládacího prvku Windows Forms, který lze přidat do seznamu ovládacích prvků pro data tabulky nebo objekty v **zdroje dat** okna, naleznete v tématu [vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje komplexní data Vytvoření vazby](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md).

## <a name="set-the-controls-to-be-created-for-data-columns-or-properties"></a>Nastavte ovládací prvky mají být vytvořeny pro datové sloupce nebo vlastnosti

Před přetažením položky, která představuje sloupci nebo vlastnosti z objektu **zdroje dat** do okna návrháře, můžete nastavit ovládací prvek, který se má vytvořit.

### <a name="to-set-the-controls-to-be-created-for-columns-or-properties"></a>Chcete-li nastavit ovládací prvky mají být vytvořeny pro sloupce nebo vlastnosti

1. Ujistěte se, **WPF** Návrhář nebo **Windows Forms** je otevřený Návrhář.

2. V **zdroje dat** okna, rozbalte položku požadovanou tabulku nebo objektu zobrazíte její sloupce nebo vlastnosti.

3. Vyberte každý sloupec nebo vlastnost, pro kterou chcete nastavit ovládací prvek, který se má vytvořit.

4. Klikněte na rozevírací nabídku pro sloupec nebo vlastnost a potom vyberte ovládací prvek, který chcete vytvořit, když je položku přetáhli do návrháře.

     Seznam dostupných ovládacích prvků, závisí na návrháře, který máte otevřený, kterou verzi rozhraní .NET váš projekt cílí, a který vlastní ovládací prvky, které podporují vytváření datových vazeb, které jste přidali do **nástrojů**. Pokud je ovládací prvek, který chcete vytvořit seznam dostupných ovládacích prvků, můžete přidat ovládací prvek do seznamu. Další informace najdete v tématu [přidání vlastních ovládacích prvků do okna zdroje dat](../data-tools/add-custom-controls-to-the-data-sources-window.md).

     Další informace o vytvoření vlastního ovládacího prvku, který lze přidat do seznamu ovládacích prvků pro datové sloupce nebo vlastnosti v **zdroje dat** okna, naleznete v tématu [vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje jednoduchou datovou vazbu](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md).

     Pokud nechcete vytvořit ovládací prvek pro sloupce nebo vlastnosti, vyberte **žádný** v rozevírací nabídce. To je užitečné, pokud chcete přetáhnout do návrháře nadřazené tabulky nebo objektu, ale nechcete zahrnout konkrétní sloupec nebo vlastnost.

## <a name="see-also"></a>Viz také:

- [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)