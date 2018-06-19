---
title: Entity Framework – nástroje v sadě Visual Studio
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 1b06b573-84aa-4458-b3f5-e238df47bf45
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 0b1d98422d9527220b54232d1180ae4b91a28e6b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31922985"
---
# <a name="entity-framework-tools-in-visual-studio"></a>Entity Framework – nástroje v sadě Visual Studio
Rozhraní Entity Framework je relační objekt mapování technologie, která umožňuje vývojářům rozhraní .NET pro práci s relačních dat s použitím objektů specifické pro doménu. Díky tomu není nutná většina kódu pro přístup k datům, který vývojáři obvykle musí vytvářet. Doporučené relační objekt mapování (ORM) modelování technologie pro nové aplikace .NET je rozhraní Entity Framework.

Entity Framework – nástroje jsou navrženy pro pomoc při vytváření aplikace Entity Framework (EF). Kompletní dokumentaci rozhraní Entity Framework se zde: [EF jádra a EF 6](/ef/).

Nástroje Entity Framework, můžete vytvořit *konceptuálního modelu* z existující databáze a pak graficky vizualizovat a upravit konceptuálního modelu. Nebo můžete graficky nejprve vytvořte Koncepční model a pak vytvořte databázi, která podporuje model. V obou případech můžete automaticky aktualizovat modelu, pokud základní změny databáze a automaticky generovat objektové vrstvě kód pro vaši aplikaci. Generování databáze a generování kódu objektové vrstvě lze přizpůsobit.

Nástroje Entity Framework se instalují jako součást **úložiště dat a zpracování** zatížení v instalačním programu Visual Studio. Můžete také nainstalovat jako součást indvidual pod **sady SDK, knihovny a rozhraní** kategorie.

Toto jsou konkrétní nástroje, které tvoří Entity Framework – nástroje v sadě Visual Studio:

-   Můžete použít [!INCLUDE[vstecado](../data-tools/includes/vstecado_md.md)]  **[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] Návrhář** (**Entity Designer**) vizuálně vytvářet a upravovat entity, přidružení, mapování a vztahy dědičnosti. **Entity Designer** vytvoří také [!INCLUDE[TLA#tla_cshrp](../data-tools/includes/tlasharptla_cshrp_md.md)] nebo [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] kód objektové vrstvě.

-   Můžete použít  **[!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] průvodce** generovat konceptuálního modelu z existující databáze a přidání informací o připojení databáze do aplikace.

-   Můžete použít **Průvodce vytvořením databáze** nejprve vytvořte Koncepční model a pak vytvořit databázi, která podporuje model.

-   Můžete použít **aktualizace Průvodce modelem** aktualizovat vaše konceptuální model modelu úložiště a mapování, pokud byly provedeny změny v původní databázi.

    > [!NOTE]
    >  Od verze sady Visual Studio 2010, nástroje Entity Framework nepodporují [!INCLUDE[ss2k](../data-tools/includes/ss2k_md.md)].

Nástroje pro generování nebo změnit soubor EDMX. Tento soubor EDMX obsahuje informace, které popisují konceptuálního modelu a modelu úložiště, mapování mezi nimi. Další informace najdete v tématu [EDMX](https://msdn.microsoft.com/data/jj650889.aspx).

[Výkonné nástroje Entity Framework](https://marketplace.visualstudio.com/items?itemName=EntityFrameworkTeam.EntityFrameworkPowerToolsBeta4) můžete vytvářet aplikace, které je nutné použít datový Model Entity. Výkonné nástroje můžete generovat Koncepční model, ověření existujícího modelu, vytvořit soubory zdrojového kódu, které obsahují třídy objektu podle konceptuálního modelu a vytvoření soubory zdrojového kódu, které obsahují zobrazení, která generuje modelu. Podrobné informace najdete v tématu [zobrazení mapování Pre-Generated](https://msdn.microsoft.com/data/dn469601.aspx).

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[ADO.NET Entity Framework](/dotnet/framework/data/adonet/ef/index)|Popisuje způsob použití [!INCLUDE[adonet_edm](../data-tools/includes/adonet_edm_md.md)] nástroje, které [!INCLUDE[adonet_ef](../data-tools/includes/adonet_ef_md.md)] poskytuje pro vytvoření aplikace.|
|[Model EDM (Entity Data Model)](/dotnet/framework/data/adonet/entity-data-model)|Obsahuje odkazy a informace o práci s daty, která používá aplikace založené na [!INCLUDE[adonet_ef](../data-tools/includes/adonet_ef_md.md)].|
|[Dokumentaci Entity Framework (EF))](https://msdn.microsoft.com/library/ee712907(v=vs.113).aspx)|Poskytuje index videa, kurzy a pokročilé dokumentace, který vám pomůže provádět většinu Entity Framework.|
|[ASP.NET 5 aplikace do nové databáze](https://docs.efproject.net/en/latest/platforms/aspnetcore/new-db.html)|Popisuje postup vytvoření nové aplikace ASP.NET 5 pomocí Entity Framework 7.|

## <a name="see-also"></a>Viz také

- [Visual Studio Data Tools for .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)