---
title: 'Postupy: rozšíření kód vygenerovaný návrháře O-R'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d6d1122e-2f55-4607-8d8b-48c3c22600fb
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 0210037cdd554838c9fe08c424f02b081c6f2e1a
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="how-to-extend-code-generated-by-the-or-designer"></a>Postupy: rozšíření kód vygenerovaný Návrhář relací objektů
Kód vygenerovaný [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] znovu vygeneruje při změně tříd entit a dalších objektů na plochu návrháře. Z důvodu této nové vygenerování kódu se kód, který přidáte do generovaný kód přepíše obvykle při návrháře znovu generuje kód. [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] Poskytuje možnost pro vygenerování souborů třídu, ve které můžete přidat kód, který nedojde k přepsání. Příkladem přidání vlastního kódu pro kód vygenerovaný [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] je přidání ověření dat pro LINQ na třídy SQL (entita). Informace najdete v tématu [postupy: přidávání ověření do tříd entit](../data-tools/how-to-add-validation-to-entity-classes.md).

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="adding-code-to-an-entity-class"></a>Přidání kódu pro třídu Entity

#### <a name="to-create-a-partial-class-and-add-code-to-an-entity-class"></a>Vytvoření konkrétní třídu a přidejte kód pro třídu entity

1.  Otevřít nebo vytvořit nové technologie LINQ to SQL třídy souboru (**dbml** souboru) v [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. (Dvakrát klikněte **dbml** souboru v **Průzkumníku řešení**/**Průzkumník databáze**.)

2.  V [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], klikněte pravým tlačítkem na třídu, pro který chcete přidat ověřování a potom klikněte na **kód zobrazení**.

     Otevře se Editor kódu s konkrétní třídu pro třídu vybrané entity.

3.  Přidání kódu v deklaraci částečné třídy pro třídu entity.

## <a name="adding-code-to-a-datacontext"></a>Přidání kódu k DataContext

#### <a name="to-create-a-partial-class-and-add-code-to-a-datacontext"></a>Vytvoření konkrétní třídu a přidejte do DataContext kód

1.  Otevřít nebo vytvořit nové technologie LINQ to SQL třídy souboru (**dbml** souboru) v [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. (Dvakrát klikněte **dbml** souboru v **Průzkumníku řešení**/**Průzkumník databáze**.)

2.  V [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], klikněte pravým tlačítkem myši na prázdnou oblast na návrháře a pak klikněte na tlačítko **kód zobrazení**.

     Editor kódu otevře s konkrétní třídu pro DataContext.

3.  Přidejte do deklarací částečné třídy DataContext vašeho kódu.

## <a name="see-also"></a>Viz také

- [Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Návod: Vytváření třídy LINQ to SQL (Návrhář O-R)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)