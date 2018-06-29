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
ms.openlocfilehash: 53829ffaeab44eb758b1850f5619de43db31e589
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089682"
---
# <a name="how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-or-designer"></a>Postupy: vytvoření metody DataContext namapované na uložené procedury a funkce (Návrhář relací objektů)
Můžete přidat uložené procedury a funkce **Návrhář relací objektů** jako <xref:System.Data.Linq.DataContext> metody. Volání metody a předávání v požadované parametry spouští uložená procedura nebo funkce v databázi a vrací data v návratový typ <xref:System.Data.Linq.DataContext> metoda. Podrobné informace o <xref:System.Data.Linq.DataContext> metody, najdete v části [DataContext metody (Návrhář relací objektů)](../data-tools/datacontext-methods-o-r-designer.md).

> [!NOTE]
>  Můžete také pomocí uložených procedur přepsat výchozí nastavení [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] modul runtime chování, které provádí vložení, aktualizace a odstraní se po uložení změn z tříd entit k databázi. Další informace najdete v tématu [postupy: přiřazení uložené procedury k provedení aktualizací, vložení a odstranění (Návrhář relací objektů)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).

## <a name="create-datacontext-methods"></a>Vytvoření DataContext metody
 Můžete vytvořit <xref:System.Data.Linq.DataContext> metody přetažením uložené procedury nebo funkce z ** Průzkumníka serveru nebo **Průzkumník databáze** na **Návrhář relací objektů**.

> [!NOTE]
>  Návratový typ vygenerovaného <xref:System.Data.Linq.DataContext> metoda se liší v závislosti na tom, kde vyřadit uložená procedura nebo funkce na **Návrhář relací objektů**. Odstranit položky přímo do existující třídy entity vytvoří <xref:System.Data.Linq.DataContext> metoda s návratovým typem třídy entity. Odstranit položky na prázdnou oblast **Návrhář relací objektů** vytvoří <xref:System.Data.Linq.DataContext> metoda, která vrátí typ automaticky generované. Můžete změnit návratový typ <xref:System.Data.Linq.DataContext> metoda po jejím přidáním do **metody** podokně. Zkontrolovat nebo změnit návratový typ <xref:System.Data.Linq.DataContext> metoda, vyberte ho a zkontrolujte **návratového typu** vlastnost **vlastnosti** okno. Další informace najdete v tématu [postupy: Změna návratový typ metody DataContext (Návrhář relací objektů)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md).

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-create-datacontext-methods-that-return-automatically-generated-types"></a>Vytvoření DataContext metody, které vracejí automaticky generovaných typy

1.  V **Průzkumníka serveru** nebo **Průzkumník databáze**, rozbalte **uložené procedury** uzlu databáze, se kterým pracujete.

2.  Vyhledejte požadovanou uložené procedury a přetáhněte ji na prázdnou oblast **Návrhář relací objektů**.

     <xref:System.Data.Linq.DataContext> Metoda se vytvoří s automaticky generovaným návratový typ a zobrazí se v **metody** podokně.

### <a name="to-create-datacontext-methods-that-have-the-return-type-of-an-entity-class"></a>Chcete-li vytvořit DataContext metody, které mají návratový typ třídu entity

1.  V **Průzkumníka serveru** nebo **Průzkumník databáze**, rozbalte **uložené procedury** uzlu databáze, se kterým pracujete.

2.  Vyhledejte požadovanou uložené procedury a přetáhněte ji na existující třídy entity v **Návrhář relací objektů**.

     <xref:System.Data.Linq.DataContext> Metoda je vytvořena s návratovým typem třídy vybrané entity a zobrazí se v **metody** podokně.

> [!NOTE]
>  Informace o změně návratový typ existující <xref:System.Data.Linq.DataContext> metody, najdete v části [postupy: Změna návratový typ metody DataContext (Návrhář relací objektů)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md).

## <a name="see-also"></a>Viz také:

- [Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Metody DataContext (Návrhář relací objektů)](../data-tools/datacontext-methods-o-r-designer.md)
- [Návod: Vytvoření LINQ na SQL třídy](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Úvod do LINQ v jazyku Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)
- [LINQ v jazyce C#](/dotnet/csharp/linq/linq-in-csharp)