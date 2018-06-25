---
title: Vytváření vyhledávacích tabulek v aplikacích Windows Forms
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- lookup tables
- lookup tables, creating
ms.assetid: 0edd5385-c381-4b17-9096-74e2778db9d5
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 7b154b970d2a738e80efa5cbf669d29bd7bae589
ms.sourcegitcommit: 30f653d9625ba763f6b58f02fb74a24204d064ea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2018
ms.locfileid: "36756763"
---
# <a name="create-lookup-tables-in-windows-forms-applications"></a>Vytváření vyhledávacích tabulek v aplikacích Windows Forms
Termín *vyhledávací tabulky* popisuje ovládací prvky vázané na dva souvisejících dat tabulky. Tyto vyhledávací ovládací prvky zobrazují data v první tabulce na základě hodnoty vybrané v druhé tabulce.

 Vyhledávací tabulky můžete vytvořit tak, že přetáhnete hlavní uzel nadřazené tabulky (z [okno zdroje dat](add-new-data-sources.md)) na ovládací prvek na formuláři, který je již vázána na sloupec v tabulce souvisejících podřízených.

 Předpokládejme například tabulku `Orders` v prodejní databázi. Každý záznam v `Orders` tabulka obsahuje `CustomerID`, která určuje, které zákazníka umístit pořadí. `CustomerID` je cizí klíč odkazující na záznam zákazníka v tabulce `Customers`. V tomto scénáři můžete rozšířit `Orders` tabulky v **zdroje dat** okna a nastavte hlavní uzel na **podrobnosti**. Potom nastavte `CustomerID` sloupec používat <xref:System.Windows.Forms.ComboBox> (nebo všechny ostatní ovládací prvek, který podporuje vyhledávání vazby) a přetáhněte ji `Orders` uzlu do formuláře. Nakonec přetáhněte `Customers` uzlu na ovládací prvek, který je vázána na sloupec v relaci – v takovém případě <xref:System.Windows.Forms.ComboBox> vázána `CustomerID` sloupec.

## <a name="to-databind-a-lookup-control"></a>Vytvoření datové vazby ovládacího prvku vyhledávání

1.  Otevřete **zdroje dat** okno.

    > [!NOTE]
    >  Vyhledávací tabulky vyžadují dvě tabulky v relaci nebo objekty jsou k dispozici v **zdroje dat** okno. Další informace najdete v tématu [vztahy v datových sadách](relationships-in-datasets.md).

2.  Rozbalte uzly v **zdroje dat** okno, dokud se nezobrazí v nadřazené tabulce a všechny její sloupce a související podřízené tabulky a všechny své sloupce.

    > [!NOTE]
    >  Uzel podřízené tabulky je uzel, který je zobrazen v podřízeném uzlu, který lze rozbalit v nadřazené tabulce.

3.  Změňte typ podřízené tabulky k **podrobnosti** výběrem **podrobnosti** ze seznamu ovládací prvek v podřízené tabulce uzlu. Další informace najdete v tématu [nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdroje dat](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).

4.  Vyhledejte uzel, který má vztah dvou tabulek ( `CustomerID` uzlu v předchozím příkladu). Změnit typ rozevírací k <xref:System.Windows.Forms.ComboBox> výběrem **ComboBox** ze seznamu řízení.

5.  Přetáhněte uzel hlavní podřízené tabulky z **zdroje dat** okna do svého formuláře.

     Na formuláři se zobrazí ovládací prvky s datovou vazbou (včetně popisků) a pruh nástrojů (<xref:System.Windows.Forms.BindingNavigator>). A [datovou sadu](../data-tools/dataset-tools-in-visual-studio.md), [TableAdapter](../data-tools/create-and-configure-tableadapters.md), <xref:System.Windows.Forms.BindingSource>, a <xref:System.Windows.Forms.BindingNavigator> se zobrazí v okně komponent.

6.  Nyní, přetáhněte hlavní nadřazený uzel tabulky z **zdroje dat** okna přímo do ovládacího prvku vyhledávání ( <xref:System.Windows.Forms.ComboBox>).

     Nyní jsou vytvořeny vazby vyhledávání. Naleznete v následující tabulce pro konkrétní vlastnosti, které byly nastavené na ovládací prvek.

    |Vlastnost|Vysvětlivky k nastavení|
    |--------------|----------------------------|
    |**Zdroj dat**|Visual Studio tato vlastnost nastaví na <xref:System.Windows.Forms.BindingSource>, které byly vytvořeny pro tabulku přetáhněte do ovládacího prvku (Naproti tomu <xref:System.Windows.Forms.BindingSource>, vytvoření ovládacího prvku v okamžiku vytvoření).<br /><br /> Pokud potřebujete provést úpravu, nastavte na <xref:System.Windows.Forms.BindingSource> tabulky se sloupcem chcete zobrazit.|
    |**DisplayMember**|Aplikace Visual Studio nastaví tuto vlastnost na první sloupec po primárním klíči, který má datový typ řetězec, u tabulky, která je přetažena na ovládací prvek.<br /><br /> Pokud potřebujete provést úpravu, nastavte na název sloupce, které chcete zobrazit.|
    |**ValueMember**|Aplikace Visual Studio nastaví tuto vlastnost na první sloupec, který je součástí primárního klíče, nebo na první sloupec v tabulce, pokud není definován žádný klíč.<br /><br /> Pokud potřebujete provést úpravu, nastavte hodnotu primární klíč v tabulce s sloupec, který chcete zobrazit.|
    |**SelectedValue**|Visual Studio tato vlastnost nastaví na původní sloupec vyřadit z **zdroje dat** okno.<br /><br /> Pokud potřebujete provést úpravu, nastavením sloupec cizího klíče v tabulce v relaci.|

## <a name="see-also"></a>Viz také:

- [Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)