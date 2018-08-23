---
title: Komentáře
description: Tento článek popisuje použití komentářů v editoru zdrojového kódu sady Visual Studio pro Mac
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 0FE5E929-1846-4F48-B5E3-70990FAF9504
ms.openlocfilehash: 28c02f7f6347da67133a82c1d0aa71d44a4309d2
ms.sourcegitcommit: 2597236a481afbaf1ad4915743898ee1aee49760
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/10/2018
ms.locfileid: "42624007"
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
