---
title: Možnosti, textový editor, C#, upřesnit
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Outlining
- VS.ToolsOptionsPages.Text_Editor.CSharp.Advanced
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 010f2a2e6dc163f24a29e8e352b21d8ef8d72b48
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55927513"
---
# <a name="options-text-editor-c-advanced"></a>Možnosti, textový editor, C#, upřesnit

Použití **Upřesnit** stránka Možnosti, chcete-li změnit nastavení editoru formátování, refaktoringu kódu a komentáře dokumentace XML pro jazyk C#. Chcete-li získat přístup k této stránce Možnosti, zvolte **nástroje** > **možnosti**a klikněte na tlačítko **textový Editor** > **jazyka C#**  >  **Advanced**.

> [!NOTE]
> Ne všechny možnosti mohou být uvedeny zde.

## <a name="analysis"></a>Analýza

- Povolení úplné analýzy řešení

   Umožňuje analýzu kódu u všech souborů v řešení, ne jenom otevřít soubory kódu. Další informace najdete v tématu [úplné analýzy řešení](../../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md).

## <a name="using-directives"></a>Direktivy using

- Umístit nejdřív direktivy "System", při řazení direktiv Using

   Pokud je vybráno, **odebrat a seřadit direktivy using** příkaz v nabídce seřadí klikněte pravým tlačítkem `using` direktivy a místa obory názvů "Systém" v horní části seznamu.

   Před řazením:

   ```csharp
   using AutoMapper;
   using FluentValidation;
   using System.Collections.Generic;
   using System.Linq;
   using Newtonsoft.Json;
   using System;
   ```

   Po seřazení:

   ```csharp
   using System;
   using System.Collections.Generic;
   using System.Linq;
   using AutoMapper;
   using FluentValidation;
   using Newtonsoft.Json;
   ```

- Oddělovat skupiny direktiv using

   Pokud je vybráno, **odebrat a seřadit direktivy using** odděluje příkazu v místní nabídce `using` direktivy vložením prázdný řádek mezi skupinami direktivy, které mají stejný obor názvů root.

   Před řazením:

   ```csharp
   using AutoMapper;
   using FluentValidation;
   using System.Collections.Generic;
   using System.Linq;
   using Newtonsoft.Json;
   using System;
   ```

   Po seřazení:

   ```csharp
   using AutoMapper;

   using FluentValidation;

   using Newtonsoft.Json;

   using System;
   using System.Collections.Generic;
   using System.Linq;
   ```

- Navrhnout použití typů v sestaveních reference
- Navrhnout použití typů v balíčcích NuGet

   Když tyto možnosti jsou vybrané, [rychlá akce](../quick-actions.md) je k dispozici pro instalaci balíčku NuGet a přidejte `using` směrnice pro neodkazovaný typy.

   ![Rychlé akce pro instalaci balíčku NuGet v sadě Visual Studio](media/nuget-lightbulb.png)

## <a name="highlighting"></a>Zvýraznění

- Zvýrazňovat odkazy na _symbol pod kurzorem

   Když se kurzor uvnitř symbol, nebo když kliknete na symbol, jsou zvýrazněny všechny instance tohoto symbolu v souboru kódu.

## <a name="outlining"></a>Sbalování

- Po otevření souborů vstoupit do režimu sbalování

   Pokud je vybráno, automaticky popisuje, jak soubor kódu, který vytvoří sbalitelnou bloky kódu. Při prvním otevření souboru #regions bloky a bloky neaktivního kódu sbalte.

- Zobrazit oddělovače řádků procedury

   Textový editor označuje visual oboru postupy. Řádek je vykreslen v *.cs* zdrojové soubory vašeho projektu v umístěních uvedených v následující tabulce:

   |Umístění ve zdrojovém souboru .cs|Příklad umístění řádku|
   |---------------------------------|------------------------------|
   |Po uzavření bloku deklarace konstruktoru|– Na konci třída, struktura, modul, rozhraní nebo výčet<br />-After vlastnost, funkce nebo procedury sub<br />-Není mezi get a set klauzule ve vlastnosti|
   |Po sadu konstrukce jeden řádek|-After příkazy pro import, před definici typu v souboru třídy<br />-After proměnné deklarované ve třídě, před všechny postupy|
   |Po jeden řádek deklarací (deklarace mimo blok úrovně)|-Následující příkazy pro import, dědí příkazy deklarace proměnných, deklarace události, delegát deklarace a příkazy deklarovat knihovny DLL|

## <a name="block-structure-guides"></a>Vodítka pro strukturu bloku

Pomocí těchto zaškrtávacích políček zobrazíte tečkovaná svislé čáry mezi složené závorky (**{}**) ve vašem kódu. Můžete snadno zobrazí jednotlivé bloky kódu pro deklaraci úroveň a úroveň kód konstrukce.

## <a name="editor-help"></a>Nápověda k editoru

- Generování komentářů k dokumentaci XML pro / / / / /

   Pokud je vybráno, vloží prvky XML pro dokumentační komentáře XML po zadání `///` Úvod komentář. Další informace o dokumentaci XML, naleznete v tématu [XML – dokumentační komentáře (C# Programming Guide)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments).

## <a name="see-also"></a>Viz také:

- [Postupy: Vložit komentáře XML pro generování dokumentace](../../ide/reference/generate-xml-documentation-comments.md)
- [XML – dokumentační komentáře (C# Programming Guide)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)
- [Dokumentaci kódu pomocí komentářů XML (Průvodce v C#)](/dotnet/csharp/codedoc)
- [Nastavení možností editoru pro konkrétní jazyk](../../ide/reference/setting-language-specific-editor-options.md)
- [C# IntelliSense](../../ide/visual-csharp-intellisense.md)
