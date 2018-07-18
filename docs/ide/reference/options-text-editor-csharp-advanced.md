---
title: Možnosti, textový editor, C#, upřesnit
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Outlining
- VS.ToolsOptionsPages.Text_Editor.CSharp.Advanced
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: ab08de0c6993f57c719f69ccf27e30e3cbe41c32
ms.sourcegitcommit: 80f9daba96ff76ad7e228eb8716df3abfd115bc3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2018
ms.locfileid: "37433299"
---
# <a name="options-text-editor-c-advanced"></a>Možnosti, textový editor, C#, upřesnit

Použití **Upřesnit** stránka Možnosti, chcete-li změnit nastavení editoru formátování, refaktoringu kódu a komentáře dokumentace XML pro jazyk C#. Chcete-li získat přístup k této stránce Možnosti, zvolte **nástroje** > **možnosti**a klikněte na tlačítko **textový Editor** > **jazyka C#**  >  **Advanced**.

> [!NOTE]
> Ne všechny možnosti mohou být uvedeny zde.

## <a name="analysis"></a>Analýza

- Povolení úplné analýzy řešení

   Umožňuje analýzu kódu u všech souborů v řešení, ne jenom otevřít soubory kódu. Další informace najdete v tématu [úplné analýzy řešení](../../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md).

## <a name="highlighting"></a>Zvýraznění

- Zvýrazňovat odkazy na _symbol pod kurzorem

   Když se kurzor uvnitř symbol, nebo když kliknete na symbol, jsou zvýrazněny všechny instance tohoto symbolu v souboru kódu.

## <a name="outlining"></a>Sbalování

- Po otevření souborů vstoupit do režimu sbalování

   Pokud je vybráno, automaticky popisuje, jak soubor kódu, který vytvoří sbalitelnou bloky kódu. Při prvním otevření souboru #regions bloky a bloky neaktivního kódu sbalte.

## <a name="editor-help"></a>Nápověda k editoru

- Generování komentářů k dokumentaci XML pro / / / / /

   Pokud je vybráno, vloží prvky XML pro dokumentační komentáře XML po zadání `///` Úvod komentář. Další informace o dokumentaci XML, naleznete v tématu [XML – dokumentační komentáře (C# Programming Guide)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments).

## <a name="see-also"></a>Viz také:

- [Postupy: vložení komentáře XML pro generování dokumentace](../../ide/reference/generate-xml-documentation-comments.md)
- [XML – dokumentační komentáře (C# Programming Guide)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)
- [Dokumentaci kódu pomocí komentářů XML (Průvodce v C#)](/dotnet/csharp/codedoc)
- [Nastavení možností editoru pro konkrétní jazyk](../../ide/reference/setting-language-specific-editor-options.md)
- [C# IntelliSense](../../ide/visual-csharp-intellisense.md)