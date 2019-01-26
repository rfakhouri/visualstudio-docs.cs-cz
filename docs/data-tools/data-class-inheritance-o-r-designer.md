---
title: Dědičnost datových tříd (Návrhář O-R)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: af32653c-f4e6-4217-8c5a-e32b322b4918
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: f0e95466baa4e16e4620ff387a11d4e723399a38
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54953390"
---
# <a name="data-class-inheritance-or-designer"></a>Dědičnost datových tříd (Návrhář O/R)

Jako u jiných objektů třídy LINQ to SQL můžete použít dědičnosti a být odvozen od jiných tříd. V kódu můžete zadat dědičnosti relací mezi objekty deklarací, že jedna třída dědí z jiné. V databázi vztahy dědičnosti vytvoří několika způsoby. **Návrhář relací objektů** (**O/R Designer**) podporují koncept dědičnosti jedné tabulky, jak často je implementován v relačních systémech.

V dědičnosti jedné tabulky je izolované databáze tabulku, která obsahuje sloupce pro základní a odvozené třídy. S relačními daty rozlišující sloupec obsahuje hodnotu, která určuje, které třídě daný záznam patří. Představte si třeba `Persons` tabulku, která obsahuje všechny uživatele náhradník společnosti. Někteří lidé jsou zaměstnanci a někteří lidé jsou správci. `Persons` Tabulka obsahuje sloupec s názvem `Type` , který má hodnotu 1 pro manažery a hodnota 2 pro zaměstnance. `Type` Sloupec je sloupec diskriminátoru. V tomto scénáři můžete vytvořit podtřídu zaměstnanců a naplnit třída se pouze záznamy, které mají `Type` hodnota 2.

Při konfiguraci dědičnosti tříd entit pomocí [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], přetáhněte jednu tabulku, která obsahuje data dědičnosti na Návrhář dvakrát: jednou pro každou třídu v hierarchii dědičnosti. Po přidání tabulky do návrháře spojujeme je s dědičnosti položky z **Návrhář relací objektů** nástrojů a pak nastavit čtyři vlastnosti dědičnosti v **vlastnosti** okna.

## <a name="inheritance-properties"></a>Dědičnost vlastnosti

V následující tabulce jsou uvedeny dědičnosti vlastností a jejich popis:

|Vlastnost|Popis|
|--------------|-----------------|
|**Vlastnost diskriminátoru**|Vlastnost (mapována na sloupec), která určuje, která třída aktuální záznam patří.|
|**Hodnota diskriminátoru základní třídy**|Hodnota (ve sloupci určený jako **vlastnost diskriminátoru**), který určuje, že záznam je základní třídy.|
|**Hodnota diskriminátor odvozené třídy**|Hodnota (ve vlastnosti určené jako **vlastnost diskriminátoru**), který zjistí, že záznam odvozené třídy.|
|**Výchozí hodnota dědičnosti**|Třídy, který je vyplněný, když hodnota ve vlastnosti určené jako **vlastnost diskriminátoru** neodpovídá buď **hodnota diskriminátoru základní třídy** nebo **odvozených tříd Hodnota diskriminátoru**.|

Vytvoření objektu modelu, který používá dědičnosti a odpovídá na relační data, může být trochu matoucí. Toto téma obsahuje informace o základních konceptech a jednotlivé vlastnosti, které jsou potřeba ke konfiguraci dědičnosti. Následující témata obsahují jasnější vysvětlení, jak nakonfigurovat dědičnosti s **O/R Designer**.

|Téma|Popis|
|-----------|-----------------|
|[Postupy: Konfigurace dědičnosti pomocí Návrháře relací objektů](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)|Popisuje postup konfigurace tříd entit, které používají jedné tabulky dědičnosti pomocí **O/R Designer**.|
|[Návod: Vytvoření LINQ na třídy SQL s použitím dědičnosti jedné tabulky (O/R Designer)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)|Obsahuje podrobné pokyny o tom, jak nakonfigurovat tříd entit, které používají jedné tabulky dědičnosti pomocí **O/R Designer**.|

## <a name="see-also"></a>Viz také:

- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [Návod: Vytvoření LINQ na třídy SQL (Návrhář O-R)](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [Návod: Vytvoření LINQ na třídy SQL s použitím dědičnosti jedné tabulky (O/R Designer)](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)
- [Začínáme](/dotnet/framework/data/adonet/sql/linq/getting-started)