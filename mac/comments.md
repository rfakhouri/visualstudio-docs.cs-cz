---
title: Komentáře
description: Tento článek popisuje použití komentářů v editoru zdroje sady Visual Studio pro Mac
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: 0FE5E929-1846-4F48-B5E3-70990FAF9504
ms.openlocfilehash: 4a7dfd0daaddad9f91d461689a0174469dd253c2
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
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
