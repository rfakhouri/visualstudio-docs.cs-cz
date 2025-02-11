---
title: Logické a rozšířené operátory ve vyhledávacích výrazech (Help Viewer)
ms.date: 11/02/2017
ms.topic: reference
helpviewer_keywords:
- Help Viewer, logical operators in search
- logical operators in search [Help Viewer]
ms.assetid: 0c38ae7d-3e20-4d47-a020-9677cd285916
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0e241df6c32fc1b0a8e88942fe5d0d178c37b9bf
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67824900"
---
# <a name="logical-and-advanced-operators-in-search-expressions"></a>Logické a rozšířené operátory ve vyhledávacích výrazech

Můžete použít logické operátory a operátory rozšířeného hledání upřesněte hledání obsahu nápovědy v **aplikace Help Viewer**.

## <a name="logical-operators"></a>Logické operátory

Logické operátory určují, jak více podmínek vyhledávání by měly být kombinované vyhledávacího dotazu. Následující tabulka uvádí logické operátory AND, OR a není a BLÍZKOSTI.

|K vyhledání|Použití|Příklad|Výsledek|
|-------------------|---------|-------------|------------|
|Oba výrazy ve stejném článku|AND|DIB a palety|Témata, které obsahují "dib" a "palety".|
|Buď výraz v článku|NEBO|rastrové vektoru OR|Témata, které obsahují "rastrové" nebo "vektorové".|
|První výraz bez druhý výraz ve stejném článku|NOT|"operační systém" není DOS|Témata, které obsahují "operační systém", ale ne "DOS".|
|Oba výrazy blízko sebe v článku|V BLÍZKOSTI|uživatel TÉMĚŘ jádra|Témata, která obsahují "user" v blízkosti "jádra".|

> [!IMPORTANT]
> Logické operátory je nutné zadat velkými písmeny pro vyhledávače rozpoznány.

## <a name="advanced-operators"></a>Pokročilí operátoři

Operátory rozšířeného hledání upřesněte hledání pro obsah tak, že zadáte umístění v článku hledat hledaný termín. Následující tabulka popisuje čtyři operátory rozšířeného vyhledávání k dispozici.

|K vyhledání|Použití|Příklad|Výsledek|
|-------------------|---------|-------------|------------|
|Výraz v název článku|`title:`|`title:binaryreader`|Témata, které obsahují "binaryreader" v názvech.|
|Termín v příkladu kódu|`code:`|`code:readdouble`|Témata, které obsahují "readdouble" v příkladu kódu.|
|Výraz v příklad konkrétní programovací jazyk|`code:vb:`|`code:vb:string`|Témata, které obsahují "string" v příkladu kódu jazyka Visual Basic.|
|Článek, který je spojen s klíčovým slovem konkrétního indexu|`keyword:`|`keyword:readbyte`|Témata, které jsou spojeny s klíčovým slovem "readbyte" index.|

> [!IMPORTANT]
> Je nutné zadat operátory rozšířeného vyhledávání konečné dvojtečku žádné použité mezeru před dvojtečku pro vyhledávací web rozpoznány.

### <a name="programming-languages-for-code-examples"></a>Programovací jazyky pro příklady kódu

Můžete použít `code:` operátor hledání obsahu o všech různých programovacích jazyků. Pokud chcete vrátit příklady pro konkrétní programovací jazyk, použijte jednu z následujících hodnot programovací jazyk:

|Programovací jazyk|Syntaxe hledání – operátor|
| - |---------|
|Visual Basic|`code:vb`<br/>`code:visualbasic`|
|C#|`code:c#`<br/>`code:csharp`|
|C++|`code:cpp`<br/>`code:c++`<br/>`code:cplusplus`|
|F#|`code:f#`<br/>`code:fsharp`|
|JavaScript|`code:javascript`<br/>`code:js`|
|XAML|`code:xaml`|

> [!NOTE]
> `code:` Operátor vyhledá pouze obsah, který je označen popiskem, programovací jazyk, na rozdíl od obsah, který je obecně označeny jako kód.

## <a name="see-also"></a>Viz také:

- [Postupy: Vyhledávání témat](../help-viewer/find-topics.md)
- [Microsoft Help Viewer 2.2](../help-viewer/overview.md)
