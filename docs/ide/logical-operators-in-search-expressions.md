---
title: Logické operátory a pokročilé operátory ve vyhledávacích výrazech
ms.date: 11/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-help-viewer
ms.topic: reference
helpviewer_keywords:
- Help Viewer, logical operators in search
- logical operators in search [Help Viewer]
ms.assetid: 0c38ae7d-3e20-4d47-a020-9677cd285916
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: de351e019c4daacc61bbbdd2757b0f0d9a46e584
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="logical-and-advanced-operators-in-search-expressions"></a>Rozšířené a logické operátory ve vyhledávacích výrazech

Logické operátory a operátory rozšířeného vyhledávání můžete použít upřesněte hledání obsahu nápovědy v **Prohlížeč nápovědy**.

## <a name="logical-operators"></a>Logické operátory

Logické operátory určit, jak více podmínek vyhledávání by měla být kombinovány v vyhledávací dotaz. Následující tabulka uvádí logických operátorů AND, OR a není a v BLÍZKOSTI.

|K vyhledání|Použití|Příklad|Výsledek|
|-------------------|---------|-------------|------------|
|Oba termíny ve stejném článku|AND|DIB a palety|Témata, které obsahují "dib" a "palety".|
|Buď termín v článku|NEBO|rastrové nebo vektoru|Témata, které obsahují "rastrových" nebo "vector".|
|První výraz bez druhý výraz ve stejném článku|NENÍ|"operační systém" není DOS|Témata, které obsahují "operační systém", ale ne "DOS".|
|Obě podmínky, zavřete společně v článku|V BLÍZKOSTI|uživatel TÉMĚŘ jádra|Témata, které obsahují "user" v blízkosti "jádra".|

> [!IMPORTANT]
> Logické operátory je nutné zadat velkými písmeny pro vyhledávací rozpoznány.

## <a name="advanced-operators"></a>Pokročilí operátoři

Operátory rozšířeného vyhledávání upřesněte hledání obsahu zadáním kde v článku hledání hledaný termín. Následující tabulka popisuje čtyři operátory k dispozici rozšířené vyhledávání.

|K vyhledání|Použití|Příklad|Výsledek|
|-------------------|---------|-------------|------------|
|Termín v název článku|`title:`|`title:binaryreader`|Témata, které obsahují "binaryreader" v jejich názvy.|
|Termín v příklad kódu|`code:`|`code:readdouble`|Témata, které obsahují "readdouble" v příkladu kódu.|
|Termín v Příkladem konkrétní programovací jazyk|`code:vb:`|`code:vb:string`|Témata obsahující "řetězec v příklad kódu jazyka Visual Basic.|
|Článek, který je přidružen konkrétní index klíčové slovo|`keyword:`|`keyword:readbyte`|Témata, které jsou spojeny s klíčovým slovem "readbyte" index.|

> [!IMPORTANT]
> Je nutné zadat operátory rozšířeného vyhledávání s posledním dvojtečkou a žádné použité místo před dvojtečkou pro vyhledávacího webu rozpoznány.

### <a name="programming-languages-for-code-examples"></a>Programovací jazyky pro příklady kódu

Můžete použít `code:` operátor hledání obsahu o všech několik programovacích jazyků. Vrátí příklady pro konkrétní programovací jazyk, použijte jednu z následujících hodnot programovací jazyk:

|Programovací jazyk|Syntaxe vyhledávání – operátor|
|--------------------|---------|
|Visual Basic|`code:vb`<br/>`code:visualbasic`|
|C#|`code:c#`<br/>`code:csharp`|
|C++|`code:cpp`<br/>`code:c++`<br/>`code:cplusplus`|
|F#|`code:f#`<br/>`code:fsharp`|
|JavaScript|`code:javascript`<br/>`code:js`|
|XAML|`code:xaml`|

> [!NOTE]
> `code:` Operátor vyhledá pouze obsah, který je označen s popiskem programovací jazyk, a obsah, který je obecně označeny jako kód.

## <a name="see-also"></a>Viz také

- [Postupy: vyhledávání témat](how-to-search-for-topics.md)
- [Microsoft Help Viewer 2.2](microsoft-help-viewer.md)
