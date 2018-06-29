---
title: Přehled Visual Studio Návrhář relací objektů
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 45e477c0-5c6b-41f9-b2d0-2808fb4f6537
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 7c7abaa95c3b7c8f5ab78b4d58f383243b176f7a
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089409"
---
# <a name="linq-to-sql-tools-in-visual-studio"></a>Technologie LINQ to SQL nástroje v sadě Visual Studio

Technologie LINQ to SQL je první objekt relační mapování technologie vydaných společností Microsoft. Je dobře funguje v základní scénáře a nadále podporován v sadě Visual Studio, ale je již ve službě active vývoji. Pomocí LINQ to SQL při zachování starší verze aplikace, který je již používán nebo v jednoduché aplikace, které používá SQL Server a nevyžadují mapování více tabulek. Obecně platí nové aplikace by měly používat rozhraní Entity Framework, pokud je potřeba vrstva relační objekt mapper.

V sadě Visual Studio, vytvoříte na třídy SQL, které představují tabulky SQL pomocí LINQ **Návrhář relací objektů** (**Návrhář relací objektů**).

**Návrhář relací objektů** má dvě odlišné oblasti na jeho návrhové ploše: entity podokna na levé straně a metody na pravé straně. V podokně entity je hlavní návrhovou plochu, který zobrazí tříd entit a přidružení a hierarchie dědičnosti. V podokně metody se na návrhovou plochu, která zobrazuje <xref:System.Data.Linq.DataContext> metody, které jsou namapované na uložené procedury a funkce.

**Návrhář relací objektů** poskytuje návrhové ploše k vytváření [technologie LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) tříd entit a přidružení (relace), které jsou založeny na objekty v databázi. Jinými slovy **Návrhář relací objektů** vytvoří model objektů v aplikaci, která se mapuje na objekty v databázi. Také vytváří silného typu <xref:System.Data.Linq.DataContext> , odesílá a přijímá data mezi tříd entit a databází. **Návrhář relací objektů** také poskytuje funkce pro mapování uložené procedury a funkce na <xref:System.Data.Linq.DataContext> metody pro vrácení dat a tříd entit naplnění. Nakonec **Návrhář relací objektů** poskytuje možnost návrhu dědičnosti vztahy mezi třídami entity.

## <a name="open-the-or-designer"></a>Otevřít Návrhář relací objektů

Chcete-li přidat LINQ do modelu entity SQL do projektu, zvolte **projektu** > **přidat novou položku**a potom vyberte **třídy LINQ to SQL** ze seznamu položek projektu:

![Třídy LINQ to SQL](../data-tools/media/raddata-linq-to-sql-classes.png)

Visual Studio vytvoří *dbml* souboru a přidá ji do vašeho řešení. Toto je soubor XML mapování a jeho soubory související kódu.

![Technologie LINQ to SQL třídy v Průzkumníku řešení](../data-tools/media/raddata-linq-to-sql-classes-in-solution-explorer.png)

Když vyberete *dbml* souboru, Visual Studio zobrazí **Návrhář relací objektů** prostor, který umožňuje vizuálně vytvoření modelu. Následující obrázek znázorňuje Návrháře po Northwind `Customers` a `Orders` tabulky byl přetažen z **Průzkumníka serveru**. Poznámka: vztah mezi tabulkami.

![Technologie LINQ to SQL Návrháře](../data-tools/media/raddata-linq-to-sql-designer.png)

> [!IMPORTANT]
> **Návrhář relací objektů** je relační mapper jednoduchého objektu, protože ji podporuje jenom relace 1:1 mapování. Jinými slovy třídu entity může mít pouze vztah mapování 1:1 s databázové tabulky nebo zobrazení. Komplexní mapování, jako je například mapování třídu entity na připojené k tabulce nepodporuje; použijte pro komplexní mapování rozhraní Entity Framework. Kromě toho návrháře je generátor kódu jednosměrná. To znamená, že se projeví pouze změny, které provedete na plochu návrháře do souboru kódu. Ruční změny do souboru kódu se neprojeví v **Návrhář relací objektů**. Veškeré změny, které můžete provést ručně v souboru kódu přepíšou, když je uložen v návrháři a kód vygenerován znovu. Informace o tom, jak přidat uživatelský kód a rozšíření třídy generované **Návrhář relací objektů**, najdete v části [postupy: rozšíření kód vygenerovaný Návrhář relací objektů](../data-tools/how-to-extend-code-generated-by-the-o-r-designer.md).

## <a name="create-and-configure-the-datacontext"></a>Vytvořit a nakonfigurovat DataContext

Po přidání **třídy LINQ to SQL** položky na projekt a otevřete **Návrhář relací objektů**, prázdný návrhovou plochu, která reprezentuje prázdnou <xref:System.Data.Linq.DataContext> připravení nakonfigurovat. <xref:System.Data.Linq.DataContext> je nakonfigurovaná s informacemi o připojení poskytované první položka, která je přetáhnout na návrhovou plochu. Proto <xref:System.Data.Linq.DataContext> se konfiguruje pomocí informace o připojení z první položky vyřadit na návrhovou plochu. Další informace o <xref:System.Data.Linq.DataContext> najdete třída [DataContext metody (Návrhář relací objektů)](../data-tools/datacontext-methods-o-r-designer.md).

## <a name="create-entity-classes-that-map-to-database-tables-and-views"></a>Vytvořit tříd entit, které jsou namapovány na databázi tabulek a zobrazení

Můžete vytvořit tříd entit, které jsou namapované na tabulky a zobrazení, přetáhněte databázových tabulek a zobrazení z **Průzkumníka serveru** nebo **Průzkumník databáze** na **Návrhář relací objektů**. Jak je uvedeno v předchozí části, <xref:System.Data.Linq.DataContext> je nakonfigurovaná s informacemi o připojení poskytované první položka, která je přetáhnout na návrhovou plochu. Pokud následné položku, která používá jiné připojení je přidán do **Návrhář relací objektů**, můžete změnit připojení pro <xref:System.Data.Linq.DataContext>. Další informace najdete v tématu [postupy: vytvoření třídy LINQ to SQL namapované na tabulky a zobrazení (Návrhář relací objektů)](../data-tools/how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md).

## <a name="create-datacontext-methods-that-call-stored-procedures-and-functions"></a>Vytvoření DataContext metody, které volají uložené procedury a funkce

Můžete vytvořit <xref:System.Data.Linq.DataContext> metody, které volají (jsou namapované na) uložené procedury a funkce přetažením z **Průzkumníka serveru** nebo **Průzkumník databáze** na **Návrhář relací objektů** . Uložené procedury a funkce jsou přidány do **Návrhář relací objektů** jako metody <xref:System.Data.Linq.DataContext>.

> [!NOTE]
> Při přetažení uložené procedury a funkce z **Průzkumníka serveru** nebo **Průzkumník databáze** na **Návrhář relací objektů**, návratový typ vygenerovaného <xref:System.Data.Linq.DataContext> Metoda se liší v závislosti na tom, kde je vyřadit položky. Další informace najdete v tématu [DataContext metody (Návrhář relací objektů)](../data-tools/datacontext-methods-o-r-designer.md).

## <a name="configure-a-datacontext-to-use-stored-procedures-to-save-data-between-entity-classes-and-a-database"></a>Konfigurace DataContext používat k uložení dat mezi tříd entit a databáze uložené procedury

Jak jsme uvedli dříve, můžete vytvořit <xref:System.Data.Linq.DataContext> metody, které volají uložené procedury a funkce. Kromě toho můžete přiřadit také uložené procedury, které se používají pro výchozí technologie LINQ to SQL modul runtime chování, který provádí vložení, aktualizace a odstraní. Další informace najdete v tématu [postupy: přiřazení uložené procedury k provedení aktualizací, vložení a odstranění (Návrhář relací objektů)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).

## <a name="inheritance-and-the-or-designer"></a>Dědičnost a Návrhář relací objektů

Jako u jiných objektů třídy LINQ to SQL můžete použít dědičnosti a být odvozen od jiné třídy. V databázi jsou vytvořit relace dědičnosti několika způsoby. **Návrhář relací objektů** podporuje koncept dědění jedné tabulky, jak často jsou implementované v relačním systémech. Další informace najdete v tématu [postupy: Konfigurace dědičnosti pomocí Návrhář relací objektů](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md).

## <a name="linq-to-sql-queries"></a>Dotazy LINQ to SQL

Tříd entit, které jsou vytvořené **Návrhář relací objektů** jsou navrženy pro použití s [Language-Integrated query (LINQ)](/dotnet/csharp/linq/). Další informace najdete v tématu [postupy: dotaz na informace o](/dotnet/framework/data/adonet/sql/linq/how-to-query-for-information).

## <a name="separate-the-generated-datacontext-and-entity-class-code-into-different-namespaces"></a>Oddělení generovaný kód třída DataContext a entity do různých oborech názvů

**Návrhář relací objektů** poskytuje **kontextu Namespace** a **Entity Namespace** vlastnosti <xref:System.Data.Linq.DataContext>. Tyto vlastnosti určují, jaký obor názvů <xref:System.Data.Linq.DataContext> a generování kódu entity třídy do. Ve výchozím nastavení, jsou tyto vlastnosti prázdné a <xref:System.Data.Linq.DataContext> a tříd entit, které se generují do oboru názvů aplikace. Ke generování kódu do oboru názvů než obor názvů aplikace, zadejte hodnotu do **kontextu Namespace** nebo **Entity Namespace** vlastnosti.

## <a name="reference-content"></a>Odkaz na obsah

- <xref:System.Linq>
- <xref:System.Data.Linq>

## <a name="see-also"></a>Viz také:

- [Technologie LINQ to SQL (rozhraní .NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)
- [Nejčastější dotazy (rozhraní .NET Framework)](/dotnet/framework/data/adonet/sql/linq/frequently-asked-questions)