---
title: Použití uložených procedur za účelem update, insert a delete v technologii Linq to SQL O/R Designer
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e88224ab-ff61-4a3a-b6b8-6f3694546cac
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: aefe5037120636c02b8d3fa73e4ec1fc4bc02a48
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55920441"
---
# <a name="how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-or-designer"></a>Postupy: Přiřazení uložených procedur za účelem aktualizace, vložení a odstranění (O/R Designer)

Uložené procedury lze přidat do **O/R Designer** a provést, protože Typická <xref:System.Data.Linq.DataContext> metody. Můžete je také použít k přepsání výchozích LINQ na SQL chování modulu runtime, které provádí vložení, aktualizace a odstranění při uložení změn z tříd entit k databázi (například při volání <xref:System.Data.Linq.DataContext.SubmitChanges%2A> metoda).

> [!NOTE]
> Pokud uložená procedura vrátí hodnoty, které se mají odeslat klientovi (například. hodnoty vypočítané v uložené proceduře aplikace), vytvoření výstupních parametrů v uložených procedurách. Pokud nemůžete použít výstupních parametrů, zápis přepsání implementace částečné metody, aniž byste museli spoléhat na generovaný návrhářem relací objektů. Databáze vygenerovala hodnoty členů muset být nastaven na odpovídající hodnoty po úspěšném dokončení operace INSERT nebo UPDATE. Další informace najdete v tématu [odpovědnosti pro vývojáře v přepisuje výchozí chování](/dotnet/framework/data/adonet/sql/linq/responsibilities-of-the-developer-in-overriding-default-behavior).

> [!NOTE]
> Technologie LINQ to SQL zpracovává databáze vygenerovala hodnoty automaticky pro identitu (automatické zvyšování čísla), rowguidcol (GUID databáze vygenerovala) a sloupce časového razítka. Databáze vygenerovala hodnoty v jiných typech sloupců neočekávaně způsobí hodnotu null. Na návratové hodnoty generovaných databází, měli byste ručně nastavit <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> k **true** a <xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A> na jednu z následujících akcí: [AutoSync.Always](<xref:System.Data.Linq.Mapping.AutoSync.Always>), [AutoSync.OnInsert](<xref:System.Data.Linq.Mapping.AutoSync.OnInsert>), nebo [AutoSync.OnUpdate](<xref:System.Data.Linq.Mapping.AutoSync.OnUpdate>).

## <a name="configure-the-update-behavior-of-an-entity-class"></a>Konfigurace chování aktualizace třídy Entity

Ve výchozím nastavení logika aktualizace databáze (vložení, aktualizace a odstranění) se změnami, které byly provedeny k datům v technologii LINQ na třídy SQL entita poskytuje LINQ to SQL modulu runtime. Modul runtime vytvoří výchozí příkazy INSERT, UPDATE a DELETE, které jsou založeny na schéma tabulky (sloupec a informacemi o primárním klíči). Pokud výchozí chování není žádoucí, můžete provádět konfiguraci chování aktualizace přiřazením konkrétní uložené procedury k provedení potřebné vložení, aktualizace a odstranění požadované pro manipulaci s daty v tabulce. Můžete také provést generování výchozího chování není, například při mapování tříd entit na zobrazení. Nakonec můžete přepsat výchozí chování aktualizace databáze vyžaduje přístup k tabulce prostřednictvím uložené procedury.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-assign-stored-procedures-to-override-the-default-behavior-of-an-entity-class"></a>Přiřazení uložených procedur potlačit výchozí chování třídy entity

1.  Otevřít **technologie LINQ to SQL** soubor v návrháři. (Dvakrát klikněte **dbml** ve **Průzkumníka řešení**.)

2.  V **Průzkumníka serveru** nebo **Průzkumník databáze**, rozbalte **uložené procedury** a vyhledejte uložené procedury, které chcete použít pro vložení, aktualizaci nebo odstranění příkazy třídy entity.

3.  Přetáhnout uloženou proceduru na **O/R Designer**.

     Uložená procedura se přidá do podokna metody jako <xref:System.Data.Linq.DataContext> metody. Další informace najdete v tématu [metod DataContext (O/R Designer)](../data-tools/datacontext-methods-o-r-designer.md).

4.  Vyberte třídu entity, pro které chcete používat uložené procedury k provedení aktualizace.

5.  V **vlastnosti** okna, vyberte příkaz k přepsání (**vložit**, **aktualizace**, nebo **odstranit**).

6.  Klikněte na tlačítko se třemi tečkami (...) vedle slov **používat Runtime** otevřít **konfigurace chování** dialogové okno.

7.  Vyberte **přizpůsobit**.

8.  Vyberte požadovanou uloženou proceduru v **vlastní** seznamu.

9. Prohlédněte si seznam **argumenty metody** a **vlastnosti třídy** ověřit, jestli **argumenty metody** mapují na odpovídající **vlastnosti třídy**. Mapování původní argumenty metody (`Original_<ArgumentName>`) na původní vlastnosti (`<PropertyName> (Original)`) pro `Update` a `Delete` příkazy.

    > [!NOTE]
    > Ve výchozím nastavení argumenty metody mapovat na vlastnosti třídy při názvy odpovídají. Ke změně vlastnosti, kterou už neodpovídá názvy mezi tabulkou a třídu entity, budete možná muset vybrat možnost vlastnost ekvivalentní třídu pro mapování na Pokud návrháře nelze určit správné mapování.

10. Klikněte na tlačítko **OK** nebo **použít**.

    > [!NOTE]
    >  Můžete nadále konfigurovat chování pro každou kombinaci třídu a chování jako kliknete **použít** po každé změně. Pokud změníte třídy nebo chování před kliknutím na **použít**, zobrazí se dialogové okno upozornění a poskytuje možnost použít změny.

Pokud chcete vrátit k použití logiky výchozí modul runtime pro aktualizace, klikněte na tlačítko se třemi tečkami vedle **vložit**, **aktualizace**, nebo **odstranit** v příkaz **vlastnosti**  okna a pak vyberte **použít modul runtime** v **konfigurace chování** dialogové okno.

## <a name="see-also"></a>Viz také:

- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Metody DataContext](../data-tools/datacontext-methods-o-r-designer.md)
- [Technologie LINQ to SQL (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)
- [Vložení, aktualizace a odstranění operace (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/insert-update-and-delete-operations)