---
title: 'Postupy: vytvoření metody DataContext namapované na uložené procedury a funkce (Návrhář O-R)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e7ca32f1-50b3-48af-ad92-ceafd749296a
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: ffec139089f77a1d5c3ffd855e16f12b31e35c17
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-or-designer"></a>Postupy: vytvoření metody DataContext namapované na uložené procedury a funkce (Návrhář relací objektů)
Uložené procedury a funkce lze přidat do [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] jako <xref:System.Data.Linq.DataContext> metody. Volání metody a předávání v požadované parametry spouští uložená procedura nebo funkce v databázi a vrací data v návratový typ <xref:System.Data.Linq.DataContext> metoda. Podrobné informace o <xref:System.Data.Linq.DataContext> metody, najdete v části [DataContext metody (Návrhář relací objektů)](../data-tools/datacontext-methods-o-r-designer.md).

> [!NOTE]
>  Uložené procedury lze také přepsat výchozí nastavení [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] modul runtime chování, které provádí vložení, aktualizace a odstraní se po uložení změn z tříd entit k databázi. Další informace najdete v tématu [postupy: přiřazení uložené procedury k provedení aktualizací, vložení a odstranění (Návrhář relací objektů)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).

## <a name="creating-datacontext-methods"></a>Vytváření DataContext metody
 Můžete vytvořit <xref:System.Data.Linq.DataContext> metody přetažením uložené procedury nebo funkce z **Průzkumníka serveru Průzkumníka a databáze** na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].

> [!NOTE]
>  Návratový typ vygenerovaného <xref:System.Data.Linq.DataContext> metoda se liší v závislosti na tom, kde vyřadit uložená procedura nebo funkce na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. Odstranit položky přímo do existující třídy entity vytvoří <xref:System.Data.Linq.DataContext> metoda s návratovým typem třídy entity. Odstranit položky na prázdnou oblast [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] vytvoří <xref:System.Data.Linq.DataContext> metoda, která vrátí typ automaticky generované. Můžete změnit návratový typ <xref:System.Data.Linq.DataContext> metoda po jeho přidání do podokna metody. Zkontrolovat nebo změnit návratový typ <xref:System.Data.Linq.DataContext> metoda, vyberte ho a zkontrolujte **návratového typu** vlastnost **vlastnosti** okno. Další informace najdete v tématu [postupy: Změna návratový typ metody DataContext (Návrhář relací objektů)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md).

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

#### <a name="to-create-datacontext-methods-that-return-automatically-generated-types"></a>Vytvoření DataContext metody, které vracejí automaticky generovaných typy

1.  V **Průzkumníka serveru**/**Průzkumník databáze**, rozbalte **uložené procedury** uzlu databáze pracujete s.

2.  Vyhledejte požadovanou uložené procedury a přetáhněte ji na prázdnou oblast [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].

     <xref:System.Data.Linq.DataContext> Metoda se vytvoří s automaticky generovaným návratový typ a zobrazí se v **metody** podokně.

#### <a name="to-create-datacontext-methods-that-have-the-return-type-of-an-entity-class"></a>Chcete-li vytvořit DataContext metody, které mají návratový typ třídu entity

1.  V **Průzkumníka serveru**/**Průzkumník databáze**, rozbalte **uložené procedury** uzlu databáze pracujete s.

2.  Vyhledejte požadovanou uložené procedury a přetáhněte ji na existující třídy entity v [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].

     <xref:System.Data.Linq.DataContext> Metoda je vytvořena s návratovým typem třídy vybrané entity a zobrazí se v **metody** podokně.

> [!NOTE]
>  Informace o změně návratový typ existující <xref:System.Data.Linq.DataContext> metody, najdete v části [postupy: Změna návratový typ metody DataContext (Návrhář relací objektů)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md).

## <a name="see-also"></a>Viz také

- [Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Metody DataContext (Návrhář relací objektů)](../data-tools/datacontext-methods-o-r-designer.md)
- [Návod: Vytváření třídy LINQ to SQL](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Úvod do LINQ v jazyku Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)
- [LINQ v jazyce C#](/dotnet/csharp/linq/linq-in-csharp)