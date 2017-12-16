---
title: "Visual Studio Návrhář relací objektů přehled | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45e477c0-5c6b-41f9-b2d0-2808fb4f6537
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: c493a7ea448277275072ab71cf013333ccb9b4ea
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/12/2017
---
# <a name="linq-to-sql-tools-in-visual-studio"></a>Technologie LINQ to SQL nástroje v sadě Visual Studio
Technologie LINQ to SQL je první objekt relační mapování technologie vydaných společností Microsoft. Je dobře funguje v základní scénáře a nadále podporován v sadě Visual Studio, ale je již ve službě active vývoji. Pomocí LINQ to SQL při zachování starší verze aplikace, který je již používán nebo v jednoduché aplikace, které používá SQL Server a nevyžadují mapování více tabulek. Obecně platí nové aplikace by měly používat rozhraní Entity Framework, pokud je potřeba vrstva relační objekt mapper.  
  
V sadě Visual Studio vytvořte LINQ na SQL třídy, které představují tabulky SQL pomocí Návrhář relací objektů (Návrhář relací objektů).  
  
[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] Má dvě odlišné oblasti na jeho návrhové ploše: entity podokna na levé straně a metody na pravé straně. V podokně entity je hlavní návrhovou plochu, který zobrazí tříd entit a přidružení a hierarchie dědičnosti. V podokně metody se na návrhovou plochu, která zobrazuje <xref:System.Data.Linq.DataContext> metody, které jsou namapované na uložené procedury a funkce.  
  
[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] Poskytuje návrhové ploše k vytváření [technologie LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) tříd entit a přidružení (relace), které jsou založeny na objekty v databázi. Jinými slovy [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] se používá k vytvoření objektu modelu v aplikaci, která se mapuje na objekty v databázi. Také vytváří silného typu <xref:System.Data.Linq.DataContext> používané k odesílání a příjmu dat mezi tříd entit a databáze. [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] Také poskytuje funkce pro mapování uložené procedury a funkce na <xref:System.Data.Linq.DataContext> metody pro vrácení dat a tříd entit naplnění. Nakonec [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] poskytuje možnost návrhu dědičnosti vztahy mezi třídami entity.  
  
## <a name="opening-the-or-designer"></a>Otevírání Návrhář relací objektů  
 Chcete-li přidat LINQ do modelu entity SQL do projektu, zvolte **projektu**, **přidat novou položku** a potom zvolte **třídy LINQ to SQL** ze seznamu položek projektu:  
  
 ![Třídy LINQ to SQL](../data-tools/media/raddata-linq-to-sql-classes.png "raddata třídy LINQ to SQL")  
  
 Visual Studio vytvoří soubor dbml a přidá ji do vašeho řešení. Toto je soubor XML mapování a jeho soubory související kódu.  
  
 ![Technologie LINQ to SQL třídy v Průzkumníku řešení](../data-tools/media/raddata-linq-to-sql-classes-in-solution-explorer.png "raddata technologie LINQ to SQL třídy v Průzkumníku řešení")  
  
 Když vyberete soubor DBML, Visual Studio zobrazí plochu návrháře relací objektů, která umožňuje vizuálně vytvoření modelu. Následující obrázek znázorňuje Návrháře po tabulky zákazníků Northwind a objednávky byl přetažen z Průzkumníka serveru. Poznámka: vztah mezi tabulkami.  
  
 ![Technologie LINQ to SQL návrháře](../data-tools/media/raddata-linq-to-sql-designer.png "raddata technologie LINQ to SQL Návrháře")  
  
> [!IMPORTANT]
>  [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] Je relační mapper jednoduchého objektu, protože ji podporuje jenom relace 1:1 mapování. Jinými slovy třídu entity může mít pouze vztah mapování 1:1 s databázové tabulky nebo zobrazení. Komplexní mapování, jako je například mapování třídu entity na připojené k tabulce nepodporuje; použijte pro komplexní mapování rozhraní Entity Framework. Kromě toho návrháře je generátor kódu jednosměrná. To znamená, že se projeví pouze změny, které provedete na plochu návrháře do souboru kódu. Ruční změny do souboru kódu se neprojeví v [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. Veškeré změny, které můžete provést ručně v souboru kódu přepíšou, když je uložen v návrháři a kód vygenerován znovu. Informace o tom, jak přidat uživatelský kód a rozšíření třídy generované [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], najdete v části [postupy: rozšíření kód vygenerován Návrhář relací objektů](../data-tools/how-to-extend-code-generated-by-the-o-r-designer.md).  
  
## <a name="creating-and-configuring-the-datacontext"></a>Vytváření a konfiguraci DataContext  
 Po přidání **třídy LINQ to SQL** položky na projekt a otevřete [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], prázdný návrhovou plochu, která reprezentuje prázdnou <xref:System.Data.Linq.DataContext> připravení nakonfigurovat. <xref:System.Data.Linq.DataContext> je nakonfigurovaná s informacemi o připojení poskytované první položka, která je přetáhnout na návrhovou plochu... Proto <xref:System.Data.Linq.DataContext> se konfiguruje pomocí informace o připojení z první položky vyřadit na návrhovou plochu. Další informace o <xref:System.Data.Linq.DataContext> najdete třída [DataContext metody (Návrhář relací objektů)](../data-tools/datacontext-methods-o-r-designer.md).  
  
## <a name="creating-entity-classes-that-map-to-database-tables-and-views"></a>Vytváření tříd entit, které jsou namapovány na databázi tabulek a zobrazení  
 Můžete vytvořit tříd entit, které jsou namapované na tabulky a zobrazení, přetáhněte databázových tabulek a zobrazení z **Průzkumníka serveru**/**Průzkumník databáze** na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. Jak je uvedeno v předchozí části <xref:System.Data.Linq.DataContext> je nakonfigurovaná s informacemi o připojení poskytované první položka, která je přetáhnout na návrhovou plochu. Pokud následné položku, která používá jiné připojení je přidán do [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], můžete změnit připojení pro <xref:System.Data.Linq.DataContext>. Další informace najdete v tématu [postupy: vytvoření třídy LINQ to SQL namapované na tabulky a zobrazení (Návrhář relací objektů)](../data-tools/how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md).  
  
## <a name="creating-datacontext-methods-that-call-stored-procedures-and-functions"></a>Vytváření DataContext metody, které volají uložené procedury a funkce  
 Můžete vytvořit <xref:System.Data.Linq.DataContext> metody, které volají (jsou namapované na) uložené procedury a funkce přetažením z **Průzkumníka serveru**/**Průzkumník databáze** na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. Uložené procedury a funkce jsou přidány do [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] jako metody <xref:System.Data.Linq.DataContext>.  
  
> [!NOTE]
>  Při přetažení uložené procedury a funkce z **Průzkumníka serveru**/**Průzkumník databáze** na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], návratový typ vygenerovaného <xref:System.Data.Linq.DataContext> metoda se liší v závislosti na tom, kde vyřadit položky. Další informace najdete v tématu [DataContext metody (Návrhář relací objektů)](../data-tools/datacontext-methods-o-r-designer.md).  
  
## <a name="configuring-a-datacontext-to-use-stored-procedures-to-save-data-between-entity-classes-and-a-database"></a>Konfigurace DataContext používat k uložení dat mezi tříd entit a databáze uložené procedury  
 Jak jsme uvedli dříve, můžete vytvořit <xref:System.Data.Linq.DataContext> metody, které volají uložené procedury a funkce. Kromě toho můžete přiřadit také uložené procedury, které lze použít pro výchozí [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] modul runtime chování, které provádí vložení, aktualizace a odstraní. Další informace najdete v tématu [postupy: přiřazení uložené procedury k provedení aktualizací, vložení a odstranění (Návrhář relací objektů)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).  
  
## <a name="inheritance-and-the-or-designer"></a>Dědičnost a Návrhář relací objektů  
 Jako jiné objekty, [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] třídy můžete použít dědičnosti a být odvozen od jiné třídy. V databázi jsou vytvořit relace dědičnosti několika způsoby. [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] Podporuje koncept dědění jedné tabulky, jak často jsou implementované v relačním systémech. Další informace najdete v tématu [postupy: Konfigurace dědičnosti pomocí Návrhář relací objektů](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md).  
  
## <a name="linq-to-sql-queries"></a>Dotazy LINQ to SQL  
 Tříd entit, které jsou vytvořené [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] jsou navrženy pro použití s [LINQ (Language-Integrated Query)](/dotnet/csharp/linq/). Další informace najdete v tématu [postupy: dotaz na informace o](/dotnet/framework/data/adonet/sql/linq/how-to-query-for-information).  
  
## <a name="separating-the-generated-datacontext-and-entity-class-code-into-different-namespaces"></a>Rozdělit do různých oborech názvů generovaného DataContext a kód Entity – třída  
 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] Poskytuje **kontextu Namespace** a **Entity Namespace** vlastnosti <xref:System.Data.Linq.DataContext>. Tyto vlastnosti určují, jaký obor názvů <xref:System.Data.Linq.DataContext> a generování kódu entity třídy do. Ve výchozím nastavení, jsou tyto vlastnosti prázdné a <xref:System.Data.Linq.DataContext> a tříd entit, které se generují do oboru názvů aplikace. Ke generování kódu do oboru názvů než obor názvů aplikace, zadejte hodnotu do **kontextu Namespace** nebo **Entity Namespace** vlastnosti.
  
## <a name="reference-content"></a>Odkaz na obsah
<xref:System.Linq>  
<xref:System.Data.Linq>  
  
## <a name="see-also"></a>Viz také
[Technologie LINQ to SQL (rozhraní .NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)    
[Nejčastější dotazy (rozhraní .NET Framework)](/dotnet/framework/data/adonet/sql/linq/frequently-asked-questions) 