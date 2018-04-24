---
title: Komentáře
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 0FE5E929-1846-4F48-B5E3-70990FAF9504
ms.openlocfilehash: 0d49896a3c265dfdc5a25c46e80de498adfffb07
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="comments"></a>Komentáře

Při ladění nebo experimentování se kód, může být užitečné komentář bloky kódu buď dočasně nebo dlouhodobé. 

Chcete-li komentář celý blok kódu:

* Vyberte kód a vyberte **přepnutí řádku poznámkami** z místní nabídky

NEBO

* Použití `cmd + /` keybinding na vybraný úsek kódu.

Tyto metody slouží komentovat a zrušte komentář u sekcí kódu. V soubory C# možné přidat další úrovně komentáře řádku, což umožňuje oblasti kódy, které mají být komentáři a uncommented při stále zachování skutečné komentáře: 

 ![víceúrovňovou komentáře](media/source-editor-image8.png)

Komentáře jsou užitečné i pro dokumentace kódu pro budoucí vývojáře, která může komunikovat s ním. Obvykle se provádějí ve formě poznámky Víceřádkový, které jsou přidány následujícím způsobem ve všech jazycích:

**C#**

``` cs
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
