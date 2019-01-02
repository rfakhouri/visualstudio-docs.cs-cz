---
title: 'Postupy: Rozšíření kódu vygenerovaného návrhářem relací –'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d6d1122e-2f55-4607-8d8b-48c3c22600fb
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 41704ad1f43dadee1efd16102281173215bad4e0
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53933781"
---
# <a name="how-to-extend-code-generated-by-the-or-designer"></a>Postupy: Rozšíření kódu vygenerovaného návrhářem relací objektů
Kód vygenerovaný **O/R Designer** je znovu vygenerovány, když dojde ke změně tříd entit a dalších objektů na návrhové ploše. Z důvodu této opětovné generování kódu veškerý kód, který přidáte do vytvořeného kódu je obvykle při přepsat návrháře znovu vygeneruje kód. **O/R Designer** poskytuje možnost Generovat částečné třídy soubory, které můžete přidat kód, který není přepsán. Jedním z příkladů přidání vlastního kódu pro kód vygenerovaný **O/R Designer** je přidání ověření dat na LINQ na třídy SQL (entita). Další informace najdete v tématu [jak: Přidání ověřování do tříd entit](../data-tools/how-to-add-validation-to-entity-classes.md).

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="add-code-to-an-entity-class"></a>Přidejte kód do třídy entity

### <a name="to-create-a-partial-class-and-add-code-to-an-entity-class"></a>Vytvořit částečné třídy a přidat kód do třídy entity

1.  Otevřete nebo vytvořte novou LINQ na třídy SQL soubor (**dbml** souborů) v **O/R Designer**. (Dvakrát klikněte **dbml** ve **Průzkumníka řešení** nebo **Průzkumník databáze**.)

2.  V **O/R Designer**, klikněte pravým tlačítkem na třídu, pro který chcete přidat ověřování a pak klikněte na tlačítko **zobrazit kód**.

     Otevře se Editor kódu s částečnou třídu pro třídy vybranou entitu.

3.  Přidejte svůj kód v deklaraci částečné třídy pro třídu entity.

## <a name="add-code-to-a-datacontext"></a>Přidání kódu do položkou DataContext

### <a name="to-create-a-partial-class-and-add-code-to-a-datacontext"></a>Vytvoření částečné třídy a přidat kód do položkou DataContext

1.  Otevřete nebo vytvořte novou LINQ na třídy SQL soubor (**dbml** souborů) v **O/R Designer**. (Dvakrát klikněte **dbml** ve **Průzkumníka řešení** nebo **Průzkumník databáze**.)

2.  V **O/R Designer**, klikněte pravým tlačítkem na prázdnou oblast v návrháři a potom klikněte na tlačítko **zobrazit kód**.

     Otevře se Editor kódu s částečnou třídu pro DataContext.

3.  Přidejte svůj kód v deklaraci částečné třídy pro DataContext.

## <a name="see-also"></a>Viz také:

- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Návod: Vytvoření LINQ na třídy SQL (Návrhář O-R)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)