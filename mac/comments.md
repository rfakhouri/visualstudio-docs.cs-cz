---
title: Okomentujte kód
description: Tento článek popisuje použití komentářů v editoru zdrojového kódu sady Visual Studio pro Mac
author: cobey
ms.author: cobey
ms.date: 05/06/2018
ms.assetid: 0FE5E929-1846-4F48-B5E3-70990FAF9504
ms.openlocfilehash: 2966d8b89a2609d3fbfc2b6b4561288433641ca1
ms.sourcegitcommit: 7fbfb2a1d43ce72545096c635df2b04496b0be71
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/09/2019
ms.locfileid: "67693116"
---
# <a name="comments"></a>Komentáře

Při ladění nebo experimentování s kódem, může být užitečné komentáře bloky kódu buď dočasně, nebo dlouhodobě.

Chcete-li okomentujte celý blok kódu:

* Vyberte kód a vybrat **přepnout komentáře k řádkům** v místní nabídce

NEBO

* Použití `cmd + /` klávesové zkratky ve vybraném kódu.

Tyto metody slouží k komentovat a zrušte komentář u části kódu. V souborech jazyka C# další úrovně řádku komentáře lze přidat, umožňuje oblastech kódy, které mají být komentářem a neokomentovaném textu při stále zachováním skutečné komentáře:

![Víceúrovňové komentáře](media/source-editor-image8.png)

Komentáře jsou také užitečná pro dokumentaci kódu pro budoucí vývojáři, kteří mohou pracovat s ním. Obvykle se provede v podobě víceřádkových komentářů, které se přidají v každém jazyce následujícím způsobem:

**C#**

```csharp
/*
 This is a multi-line
 comment in C#
*/
```

**F#**

```fsharp
(*
 This is a multi-line
  comment in F#
*)
```

## <a name="see-also"></a>Viz také:

- [Okomentujte kód (Visual Studio na Windows)](/visualstudio/ide/quickstart-editor#comment-out-code)