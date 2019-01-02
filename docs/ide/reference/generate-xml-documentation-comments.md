---
title: Vložit komentáře dokumentace XML
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 05104b9c734b35226fcd9a964372802f351605df
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53964280"
---
# <a name="how-to-insert-xml-comments-for-documentation-generation"></a>Postupy: Vložit komentáře XML pro generování dokumentace

Visual Studio vám může pomoct dokumentovat prvků kódu, jako jsou třídy a metody, pomocí automatického generování standardní struktura komentáře dokumentace XML. V době kompilace můžete vygenerovat soubor XML, který obsahuje komentáře k dokumentaci. XML souboru generovaného kompilátorem můžete distribuovat spolu s sestavení .NET, aby Visual Studio a jiná Integrovaná vývojová prostředí pomocí technologie IntelliSense můžete zobrazit rychlé informace o typech a členech. Kromě toho lze spustit soubor XML prostřednictvím nástrojů jako [DocFX](https://dotnet.github.io/docfx/) a [Sandcastle](https://www.microsoft.com/download/details.aspx?id=10526) ke generování websites referenční dokumentace rozhraní API.

> [!NOTE]
> **Vložit komentář** příkaz, který automaticky vloží dokumentační komentáře XML je k dispozici v [ C# ](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments) a [jazyka Visual Basic](/dotnet/visual-basic/programming-guide/program-structure/how-to-create-xml-documentation). Však můžete ručně vložit [dokumentační komentáře XML v jazyce C++](/cpp/ide/xml-documentation-visual-cpp) soubory a stále Generovat soubory dokumentace XML v době kompilace.

## <a name="to-insert-xml-comments-for-a-code-element"></a>Chcete-li vložit komentáře XML pro prvek kódu

1. Umístěte kurzor nad element, který má k dokumentu, například metoda text.

1. Proveďte jednu z těchto akcí:

   - Typ `///` v C#, nebo `'''` v jazyce Visual Basic

   - Z **upravit** nabídce zvolte **IntelliSense** > **Vložit komentář**

   - Z klikněte pravým tlačítkem nebo místní nabídky nebo přímo nad prvek kódu, zvolte **fragment** > **Vložit komentář**

   XML šablony okamžitě generováno nad prvek kódu. Například když při psaní komentářů metodu, vygeneruje **\<souhrnu\>** elementu, **\<param\>** – element pro každý parametr a **\<vrátí\>** element dokumentu návratovou hodnotu.

   ![Šablona komentáře XML –C#](media/doc-preview-cs.png)

   ![Šablona komentáře XML – Visual Basic](media/doc-preview-vb.png)

1. Zadejte popis jednotlivých prvků XML do plně dokumentu na prvek kódu.

   ![Dokončené komentář](media/doc-result-cs.png)

> [!NOTE]
> Je [možnost](../../ide/reference/options-text-editor-csharp-advanced.md) pro dokumentační komentáře XML přepnout po zadání `///` v C# nebo `'''` jazyka Visual Basic. Na panelu nabídek zvolte **nástroje** > **možnosti** otevřít **možnosti** dialogové okno. Pak přejděte do **textový Editor**  >  **C#** nebo **základní** > **Upřesnit**. V **Nápověda k editoru** části, vyhledejte **generovat komentáře dokumentace XML** možnost.

## <a name="see-also"></a>Viz také:

- [XML – dokumentační komentáře (C# Programming Guide)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)
- [Dokumentace kódu s komentáři XML (C# průvodce)](/dotnet/csharp/codedoc)
- [Postupy: Vytvoření dokumentace XML (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/how-to-create-xml-documentation)
- [Komentáře v jazyce C++](/cpp/cpp/comments-cpp)
- [XML dokumentace (C++)](/cpp/ide/xml-documentation-visual-cpp)
- [Generování kódu](../code-generation-in-visual-studio.md)