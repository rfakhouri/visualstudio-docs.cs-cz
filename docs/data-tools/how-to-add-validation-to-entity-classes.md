---
title: 'Postupy: Přidání ověřování do tříd entit'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
ms.assetid: 61107da9-7fa3-4dba-b101-ae46536f52c4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: cc6aa80bf82a52e6dc67fab78349e4f58eadd627
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54941049"
---
# <a name="how-to-add-validation-to-entity-classes"></a>Postupy: Přidání ověřování do tříd entit
*Ověřování* tříd entit je proces ověření, že hodnoty zadané do datových objektů v souladu s omezeními ve schématu objektu a také pravidel stanovených pro aplikaci. Ověřování dat před odesláním aktualizace do podkladové databáze je dobrým zvykem, která snižuje chyby. Také snižuje potenciální počet výměn mezi aplikací a databáze.

 [Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md) poskytuje částečným metodám, které uživatelům umožňují rozšířit kód generovaný návrhářem, který spustí během vložení, aktualizace a odstranění kompletní entit a také během a po jednotlivých sloupců změny.

> [!NOTE]
>  Toto téma popisuje základní kroky pro přidání ověřování do tříd entit pomocí **O/R Designer**. Vzhledem k tomu může být obtížné postupovat podle následujících obecných kroků bez ohledu na konkrétní entitu třídu, je k dispozici návod, který používá skutečná data.

## <a name="add-validation-for-changes-to-the-value-in-a-specific-column"></a>Přidání ověřování pro změny s hodnotou v určitém sloupci
 Tento postup ukazuje, jak ověřit data při změně hodnoty ve sloupci. Protože ověření se provede uvnitř definice třídy (místo v uživatelském rozhraní), je vyvolána výjimka, pokud hodnota způsobí selhání ověření. Implementace zpracování chyb pro kód ve vaší aplikaci, která se pokusí změnit hodnoty ve sloupcích.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-validate-data-during-a-columns-value-change"></a>Ověření dat při změně hodnoty sloupce.

1.  Otevřete nebo vytvořte novou LINQ na třídy SQL soubor (**dbml** souborů) v **O/R Designer**. (Dvakrát klikněte **dbml** ve **Průzkumníka řešení**.)

2.  V **O/R Designer**, klikněte pravým tlačítkem na třídu, pro který chcete přidat ověřování a pak klikněte na tlačítko **zobrazit kód**.

     Otevře se Editor kódu s částečnou třídu pro třídy vybranou entitu.

3.  Umístěte kurzor do částečné třídy.

4.  Pro projekty jazyka Visual Basic:

    1.  Rozbalte **název metody** seznamu.

    2.  Vyhledejte **OnCOLUMNNAMEChanging** metodu pro sloupec, který chcete přidat k ověření.

    3.  `OnCOLUMNNAMEChanging` Metoda je přidána do částečné třídy.

    4.  Přidejte následující kód, který nejprve ověřte, zda byla zadána hodnota, a pak zajistit, aby hodnota zadaná pro sloupec je přijatelné pro vaši aplikaci. `value` Argument obsahuje navrhovanou hodnotu, takže přidání logiky pro potvrzení, že se jedná o platnou hodnotu:

        ```vb
        If value.HasValue Then
            ' Add code to ensure that the value is acceptable.
            ' If value < 1 Then
            '    Throw New Exception("Invalid data!")
            ' End If
        End If
        ```

    Pro projekty jazyka C#:

    Protože C# projekty nevytváří automaticky obslužné rutiny událostí, technologie IntelliSense můžete použít k vytvoření měnící sloupec částečné metody. Typ `partial` a pak prostor pro přístup k seznamu k dispozici částečné metody. Klikněte na metodu se měnících sloupce pro sloupec, který chcete přidat ověřování. Následující kód se podobá kód, který se vygeneruje, když vyberete částečné metody se měnící sloupec:

    ```csharp
    partial void OnCOLUMNNAMEChanging(COLUMNDATATYPE value)
        {
           throw new System.NotImplementedException();
        }
    ```

## <a name="add-validation-for-updates-to-an-entity-class"></a>Přidání ověřování pro aktualizace do třídy Entity
 Kromě kontroly toho hodnoty během změny, můžete také ověřit data při pokusu o aktualizaci třídu úplnou entitu. Ověření během pokusu o aktualizaci můžete porovnat hodnoty ve více sloupcích, pokud to vyžadují obchodní pravidla. Následující postup ukazuje, jak ověřit při pokusu o aktualizaci třídu úplnou entitu.

> [!NOTE]
>  Ověřovací kód pro aktualizace dokončete tříd entit je proveden v částečnou <xref:System.Data.Linq.DataContext> třídy (místo v dílčí třídě konkrétní entity třídy).

### <a name="to-validate-data-during-an-update-to-an-entity-class"></a>Ověření dat během aktualizace do třídy entity

1.  Otevřete nebo vytvořte novou LINQ na třídy SQL soubor (**dbml** souborů) v **O/R Designer**. (Dvakrát klikněte **dbml** ve **Průzkumníka řešení**.)

2.  Klikněte pravým tlačítkem na prázdnou oblast na **O/R Designer** a klikněte na tlačítko **zobrazit kód**.

     Otevře se Editor kódu s částečnou třídu `DataContext`.

3.  Umístěte kurzor do částečné třídy pro `DataContext`.

4.  Pro projekty jazyka Visual Basic:

    1.  Rozbalte **název metody** seznamu.

    2.  Klikněte na tlačítko **UpdateENTITYCLASSNAME**.

    3.  `UpdateENTITYCLASSNAME` Metoda je přidána do částečné třídy.

    4.  Přístup s použitím hodnot jednotlivých sloupců `instance` argument, jak je znázorněno v následujícím kódu:

        ```vb
        If (instance.COLUMNNAME = x) And (instance.COLUMNNAME = y) Then
            Dim ErrorMessage As String = "Invalid data!"
            Throw New Exception(ErrorMessage)
        End If
        ```

    Pro projekty jazyka C#:

    Protože C# projekty nevytváří automaticky obslužné rutiny událostí, technologie IntelliSense můžete použít k vytvoření částečnou `UpdateCLASSNAME` metody. Typ `partial` a pak prostor pro přístup k seznamu k dispozici částečné metody. Klikněte na metodu aktualizace pro třídu, na který chcete přidat ověřování. Následující kód se podobá kód, který se vygeneruje, když vyberete `UpdateCLASSNAME` částečné metody:

    ```csharp
    partial void UpdateCLASSNAME(CLASSNAME instance)
    {
        if ((instance.COLUMNNAME == x) && (instance.COLUMNNAME = y))
        {
            string ErrorMessage = "Invalid data!";
            throw new System.Exception(ErrorMessage);
        }
    }
    ```

## <a name="see-also"></a>Viz také:

- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Ověřování dat](../data-tools/validate-data-in-datasets.md)
- [Technologie LINQ to SQL (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)