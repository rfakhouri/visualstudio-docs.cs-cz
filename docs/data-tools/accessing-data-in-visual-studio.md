---
title: Přístup k datům v sadě Visual Studio
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- "80025080"
helpviewer_keywords:
- data [Visual Studio]
- data access [Visual Studio]
- data [C#]
- ADO.NET, data access
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: a7c7e031eb3fbe0330ab752882c8ac89eb7617bf
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="accessing-data-in-visual-studio"></a>Přístup k datům v sadě Visual Studio

V sadě Visual Studio, můžete vytvořit aplikace, které se připojují k datům v prakticky jakékoli databáze produkty nebo služby, v libovolném formátu kdekoli – v místním počítači, v místní síti nebo veřejné, privátní nebo hybridního cloudu.

Pro aplikace v jazyce JavaScript, Python, PHP, Ruby nebo C++ můžete připojit k datům jako cokoliv jiného, proveďte získáním knihovny a psaní kódu. Pro aplikace .NET Visual Studio poskytuje nástroje, které můžete použít k prozkoumat zdroje dat, vytváření modelů objekt uložení a pracovat s daty v paměti a vytvoření vazby dat s uživatelským rozhraním. Microsoft Azure poskytuje sady SDK pro .NET, Java, Node.js, PHP, Python, Ruby a mobilní aplikace a nástroje v sadě Visual Studio pro připojení k Azure Storage.

Následující seznamy shrnují jen některé z mnoha systémy databáze a úložiště, které lze použít ze sady Visual Studio. [Microsoft Azure](https://azure.microsoft.com/) nabídky jsou data služby, které zahrnují všechny zřizování a správy služby příslušné úložiště dat.  [Nástroje Azure pro sadu Visual Studio](https://www.visualstudio.com/features/azure-tools-vs.aspx) je volitelná součást, která umožňuje pracovat s Azure datová úložiště přímo ze sady Visual Studio. Většina jiných SQL a NoSQL databáze produkty, které jsou zde uvedeny, může být hostovaný na místním počítači, v místní síti nebo v Microsoft Azure na virtuálním počítači. V tomto scénáři jsou zodpovědní za správu samotná databáze.

**Microsoft Azure**

||||
|-|-|-|
|Databáze SQL|Azure Cosmos DB|Úložiště (objekty BLOB, tabulek, front, souborů)|
|Datový sklad SQL|SQL Server Stretch Database|Zařízení StorSimple|

a další...

**SQL**

||||
|-|-|-|
|SQL Server 2005-2016, včetně Express a LocalDB|Firebird|MariaDB|
|MySQL|Oracle|PostgreSQL|
|SQLite|||

a další...

**NoSQL**

||||
|-|-|-|
|Apache Cassandra|CouchDB|MongoDB|
|NDatabáze|OrientDB|RavenDB|
|VelocityDB|||

a další...

Mnoho dodavatelů databáze a třetím stranám podporují integrace sady Visual Studio pomocí balíčků NuGet. Nabídky můžete prozkoumat v nuget.org nebo prostřednictvím Správce balíčků NuGet v sadě Visual Studio (**nástroje** > **Správce balíčků NuGet** > **spravovat balíčky NuGet Balíčky pro řešení**). Další produkty databáze integrovat s Visual Studio jako rozšíření. Můžete procházet nabídky těchto v Visual Studio Marketplace přechodem na **nástroje**, **rozšíření a aktualizace** a potom vyberete **Online** v levém podokně Dialogové okno. Další informace najdete v tématu [databázi kompatibilní se systémy pro sadu Visual Studio](../data-tools/installing-database-systems-tools-and-samples.md).

> [!NOTE]
> Rozšířené podpory pro SQL Server 2005 skončila 12. dubna 2016. Není zaručeno, že data nástroje v sadě Visual Studio 2015 a novější bude pokračovat v práci s SQL Server 2005 po tomto datu. Další informace najdete v tématu [oznámení koncovým podpory pro SQL Server 2005](https://www.microsoft.com/sql-server/sql-server-2005).

## <a name="net-languages"></a>Jazyky rozhraní .NET

Všechny .NET přístup k datům, včetně v .NET Core je založena na technologii ADO.NET, sadu třídy, která definuje rozhraní pro přístup k libovolného typu zdroje dat, relačních i nerelačních. Visual Studio obsahuje několik nástrojů a návrhářů, které pracují s ADO.NET za účelem připojení k databázím, zpracovaly data a data k dispozici pro uživatele. V dokumentaci v této části popisuje, jak pomocí těchto nástrojů. Můžete také programu přímo u objektů příkazu ADO.NET. Další informace o přímé volání rozhraní API technologie ADO.NET naleznete v tématu [ADO.NET](/dotnet/framework/data/adonet/index).

Přístup k datům dokumentaci konkrétně související s technologií ASP.NET najdete v tématu [práci s daty](http://www.asp.net/web-forms/overview/presenting-and-managing-data) na webu technologie ASP.NET. Kurz použití rozhraní Entity Framework s architekturou ASP.NET MVC, najdete v části [Začínáme s Entity Framework 6 Code First pomocí MVC 5](/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/creating-an-entity-framework-data-model-for-an-asp-net-mvc-application).

Univerzální platformu Windows (UWP) aplikace v C# nebo Visual Basic můžete použít Microsoft Azure SDK pro .NET pro přístup k Azure Storage a jinými službami Azure. Třída Windows.Web.HttpClient umožňuje komunikaci s jakoukoli službu, RESTful. Další informace najdete v tématu [jak se připojit k serveru HTTP pomocí Windows.Web.Http](https://msdn.microsoft.com/library/windows/apps/dn469430.aspx).

Doporučený postup pro ukládání dat v místním počítači, je použití SQLite, který se spouští v rámci jednoho procesu jako aplikace. Pokud vrstva relační objekt mapování (ORM) je potřeba, můžete použít rozhraní Entity Framework. Další informace najdete v tématu [přístup k datům](/windows/uwp/data-access/index) v Centrum vývojářů pro Windows.

Pokud se připojujete ke službám Azure, je nutné stáhnout nejnovější [Azure SDK tools](https://azure.microsoft.com/downloads/).

### <a name="data-providers"></a>Zprostředkovatelé dat

Pro databáze na použití v ADO.NET, musí mít vlastní *zprostředkovatel dat ADO.NET* nebo jinak musí vystavit rozhraní ODBC nebo OLE DB. Společnost Microsoft poskytuje [seznam poskytovatelů dat ADO.NET](https://msdn.microsoft.com/data/dd363565) pro produkty SQL serveru, jakož i poskytovatelé rozhraní ODBC a OLE DB.

### <a name="data-modeling"></a>Modelování dat

V rozhraní .NET máte tři možnosti pro modelování a manipulace s daty v paměti po jejím načtení ze zdroje dat:

[Rozhraní Entity Framework](../data-tools/entity-data-model-tools-in-visual-studio.md) upřednostňované technologie Microsoft ORM. Můžete ho programu pro relační data jako první třídy objekty .NET. Pro nové aplikace by mělo být první možnost výchozí, pokud model je potřeba. To vyžaduje vlastní podpory z výchozí zprostředkovatel ADO.NET.

[Technologie LINQ to SQL](../data-tools/linq-to-sql-tools-in-visual-studio2.md) k objektu relační mapper starší generace. Funguje dobře pro méně složitých scénářů, ale už v active vývoj.

[Datové sady](../data-tools/dataset-tools-in-visual-studio.md) nejstarší ze tří technologií modelování. Je určený hlavně pro rychlý vývoj aplikací "forms over data", ve kterých nejsou zpracování obrovské objemy dat nebo provádění složitých dotazů nebo transformací. Objekt datové sady se skládá z DataTable a DataRow objektů, které logicky mnohem víc než objekty .NET vypadat podobně jako objekty databáze SQL. Pro poměrně jednoduché aplikace založené na zdroje dat SQL datové sady stále může být vhodné použít.

Není nutné k používání některé z těchto technologií. V některých scénářích, zejména v případě, že výkonu je velmi důležité, jednoduše můžete DataReader – objekt ke čtení z databáze a zkopírujte hodnoty, které je třeba do objektu kolekce, jako je například seznam\<T >.

## <a name="native-c"></a>Nativní C++

Aplikace C++, která se připojují k systému SQL Server by měly používat [Microsoft® ODBC ovladač 13.1 pro SQL Server](https://www.microsoft.com/download/details.aspx?id=53339) ve většině případů. Pokud jsou propojené servery, pak je nutné OLE DB a pro který používáte [SQL Server Native Client](/sql/relational-databases/native-client/sql-server-native-client). Máte přístup k jiné databáze pomocí [ODBC](https://msdn.microsoft.com/library/ms710252\(v=vs.85\).aspx) nebo přímo ovladače OLE DB. Rozhraní ODBC je rozhraní pro aktuální standardní databáze, ale většina systémů databáze poskytují vlastní funkce, které nelze získat přístup přes rozhraní ODBC. OLE DB je starší verze technologie COM přístup k datům, která je stále podporováno, ale nedoporučuje pro nové aplikace. Další informace najdete v tématu [přístup k datům v jazyce Visual C++](/cpp/data/data-access-in-cpp).

Můžete použít programy C++, které využívají služby REST [C++ REST SDK](https://github.com/Microsoft/cpprestsdk).

C++ programy, které fungují s Microsoft Azure Storage můžete použít [klienta úložiště Microsoft Azure](http://www.nuget.org/packages/wastorage).

Modelování dat&mdash;Visual Studio neposkytuje vrstvu ORM jazyka C++. [TYPU](http://www.codesynthesis.com/products/odb/) je oblíbených open-source ORM jazyka C++.

Další informace o připojení k databázím z aplikací C++, najdete v části [nástrojů Visual Studio data pro jazyk C++](../data-tools/visual-studio-data-tools-for-cpp.md). Další informace o starší verze technologií přístupu k datům Visual C++, najdete v části [přístup k datům](/cpp/data/data-access-in-cpp).

## <a name="javascript"></a>JavaScript

[JavaScript ve Visual Studiu](/scripting/javascript/javascript-language-reference) je první třídy jazyk pro vytváření aplikací pro různé platformy, aplikace UWP, cloudové služby, weby a webové aplikace. Bower, Grunt, Gulp, npm a NuGet z v sadě Visual Studio můžete použít k instalaci Oblíbené knihovny JavaScript a produkty databáze. Připojit k úložišti Azure a službám pomocí stažení sady SDK z [webu Azure](https://azure.microsoft.com/). Edge.js je knihovnu, která se připojuje ke zdrojům dat ADO.NET kódu JavaScript na straně serveru (Node.js).

## <a name="python"></a>Python

Nainstalujte [Python podporují v sadě Visual Studio](../python/overview-of-python-tools-for-visual-studio.md) vytvářet aplikace Python. Dokumentace k Azure má několik kurzy o připojení k datům, včetně následujících:

- [Django a databáze SQL v Azure](/azure/app-service/app-service-web-get-started-python)
- [Django a MySQL v Azure](/azure/app-service-web/web-sites-python-ptvs-django-mysql)
- Práce s [objekty BLOB](/azure/storage/blobs/storage-quickstart-blobs-python), [soubory](/azure/storage/files/storage-python-how-to-use-file-storage), [fronty](/azure/storage/queues/storage-python-how-to-use-queue-storage), a [tabulky (DB kosmetický salón)](/azure/cosmos-db/table-storage-how-to-use-python).

## <a name="related-topics"></a>Související témata

[Platforma Microsoft AI](https://azure.microsoft.com/overview/ai-platform/?v=17.42w)&mdash;obsahuje úvod do inteligentního cloudem Microsoftu, včetně Cortana Analytics Suite a podpora pro Internet věcí.

[Microsoft Azure Storage](/azure/storage/)&mdash;popisuje Azure Storage a jak vytvářet aplikace pomocí Azure BLOB, tabulek, front a soubory.

[Azure SQL Database](/azure/sql-database/)&mdash;popisuje, jak se připojit k databázi SQL Azure, relační databáze jako služba.

[SQL Server Data Tools](/sql/ssdt/download-sql-server-data-tools-ssdt)&mdash;popisuje nástroje, které usnadňují návrh, zkoumání, testování a nasazení připojené data aplikací a databází.

[ADO.NET](/dotnet/framework/data/adonet/index)&mdash;popisuje architekturu ADO.NET a jak pomocí třídy ADO.NET spravovat data aplikací a využívat zdroje dat a XML.

[ADO.NET Entity Framework](https://msdn.microsoft.com/data/ef)&mdash;popisuje postup vytvoření dat aplikací, které umožňují vývojářům programu pro koncepční model místo přímo na relační databázi.

[WCF Data Services 4.5](/dotnet/framework/data/wcf/index)&mdash;popisuje způsob použití [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] k nasazení služeb dat na webu nebo v intranetu, které implementují [Open Data Protocol (OData)](http://go.microsoft.com/fwlink/?LinkID=182204).

[Data v řešeních pro systém Office](../vsto/data-in-office-solutions.md)&mdash;obsahuje odkazy na témata, které vysvětlují, jak fungují data v řešeních pro systém Office. To zahrnuje informace o schématu orientované programování, ukládaní dat do mezipaměti a přístup k datům na serveru.

[LINQ (Language-Integrated Query)](/dotnet/csharp/linq/)&mdash;jsou popsány možnosti dotazu, integrované do jazyka C# a Visual Basic a společného modelu pro dotazování relačních databází, dokumentů XML, datové sady a kolekce v paměti.

[Nástroje XML v sadě Visual Studio](../xml-tools/xml-tools-in-visual-studio.md)&mdash;popisuje práci s funkcí rozhraní .NET Framework XML data, ladění XSLT, XML a architektura jazyka XML.

[XML – dokumenty a Data](/dotnet/standard/data/xml/index)&mdash;poskytuje přehled globální a integrované sadu tříd, které pracují s dokumenty XML a data v rozhraní .NET Framework.
