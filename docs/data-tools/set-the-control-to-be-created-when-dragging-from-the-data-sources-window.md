---
title: Nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdroje dat
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
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 5b1701b95f86f3645ea7d54a47f8b3c7b36b3fd4
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31922333"
---
# <a name="set-the-control-to-be-created-when-dragging-from-the-data-sources-window"></a>Nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdroje dat
Ovládací prvky vázané na data můžete vytvořit tak, že přetáhnete položky z **zdroje dat** okna do WPF designer nebo Návrhář formulářů Windows. Jednotlivé položky **zdroje dat** okno má výchozí ovládací prvek, který se vytvoří, když ji přetáhněte do návrháře. Můžete ale vytvoření různých ovládacího prvku.

## <a name="set-the-controls-to-be-created-for-data-tables-or-objects"></a>Nastavit ovládací prvky pro tabulky dat a objektů
Před přetahování položek, které představují data tabulky nebo objekty z **zdroje dat** okno, můžete zobrazit všechna data v jeden ovládací prvek, nebo zobrazíte každý sloupec nebo vlastnost v ovládacím prvku samostatné.

V tomto kontextu termín *objekt* odkazuje na vlastní obchodní objekt, entity (v Entity Data Model) nebo objekt vrácený služby.

### <a name="to-set-the-controls-to-be-created-for-data-tables-or-objects"></a>Chcete-li nastavit ovládací prvky pro tabulky dat a objektů

1.  Ujistěte se, že Návrháře WPF nebo Návrhář formulářů Windows je otevřené.

2.  V **zdroje dat** časové období, vyberte položku, která představuje tabulku dat nebo objekt, který chcete nastavit.

3.  Klikněte na rozevírací nabídku pro položku a pak klikněte na jednu z následujících položek v nabídce:

    -   Chcete-li zobrazit každé datové pole v ovládacím prvku samostatné, klikněte na tlačítko **podrobnosti**. Při přetažení položku dat do návrháře, tato akce vytvoří různé řízení vázané na data pro každý sloupec nebo vlastnost nadřazené tabulky dat nebo objekt, společně s popisky pro každý ovládací prvek.

    -   Pro zobrazení všech dat v jednom prvku, vyberte jiný ovládacího prvku v seznamu, jako **DataGrid** nebo **seznamu** v aplikaci WPF nebo **DataGridView** ve Windows Forms aplikace.

    Seznam dostupných ovládacích prvků závisí, na které Návrhář máte otevřený, kterou verzi rozhraní .NET Framework vaše cíle projektu a jestli jste přidali vlastní ovládací prvky vytvoření vazby na data podpory **sada nástrojů**. Pokud ovládací prvek, který chcete vytvořit není v seznamu dostupných ovládacích prvků, přidáte do seznamu ovládacího prvku. Další informace najdete v tématu [přidat vlastní ovládací prvky do okna zdroje dat](../data-tools/add-custom-controls-to-the-data-sources-window.md).

    Další informace o vytvoření vlastního ovládacího prvku Windows Forms, který jde přidat do seznamu ovládacích prvků pro tabulky dat a objektů v **zdroje dat** okně najdete v části [vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje rozšířené datové Vazba](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md).

## <a name="set-the-controls-to-be-created-for-data-columns-or-properties"></a>Nastavit ovládací prvky pro vlastnosti nebo datové sloupce
Před přetažením položku, která představuje sloupec nebo vlastnost objektu z **zdroje dat** okna návrháře, můžete nastavit ovládací prvek, který se má vytvořit.

#### <a name="to-set-the-controls-to-be-created-for-columns-or-properties"></a>Chcete-li nastavit ovládací prvky pro vlastnosti nebo sloupce

1.  Ujistěte se, že Návrháře WPF nebo Návrhář formulářů Windows je otevřené.

2.  V **zdroje dat** okně Rozbalit požadovanou tabulku nebo objekt zobrazíte její vlastnosti nebo sloupce.

3.  Vyberte každý sloupec nebo vlastnost, pro které chcete nastavení ovládacího prvku, který se má vytvořit.

4.  Klikněte na rozevírací nabídku pro sloupec nebo vlastnost a potom vyberte ovládací prvek, který chcete vytvořit, když je položka přetažením návrháře.

     Seznam dostupných ovládacích prvků závisí, na které Návrhář máte otevřený, kterou verzi rozhraní .NET Framework vaše cíle projektu a který vlastní Určuje, které podporují datové vazby jste přidali do **sada nástrojů**. Pokud ovládací prvek, který chcete vytvořit v seznamu dostupných ovládacích prvků, přidáte do seznamu ovládacího prvku. Další informace najdete v tématu [přidat vlastní ovládací prvky do okna zdroje dat](../data-tools/add-custom-controls-to-the-data-sources-window.md).

     Se dozvíte, jak vytvořit vlastní ovládací prvek, který jde přidat do seznamu ovládacích prvků pro datové sloupce nebo vlastnosti **zdroje dat** okně najdete v části [vytvoření uživatelského ovládacího prvku Windows Forms, který podporuje jednoduchou datovou vazbu](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md).

     Pokud nechcete, aby k vytvoření ovládacího prvku na sloupec nebo vlastnost, vyberte **žádné** v rozevírací nabídce. To je užitečné, pokud chcete do návrháře přetáhněte nadřazenou tabulkou nebo objekt, ale nechcete patří konkrétní sloupec nebo vlastnost.

## <a name="see-also"></a>Viz také

- [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)