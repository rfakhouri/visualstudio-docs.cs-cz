---
title: Vložit dokumentační komentáře XML v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 01/26/2018
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 0fae2411a77f405404e34c7a2357554c1e5398ab
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-insert-xml-comments-for-documentation-generation"></a>Postupy: vložení komentáře XML pro dokumentaci generování

Visual Studio může pomoct dokumentu elementy kódu, jako jsou třídy a metody, pomocí automatického generování standardní struktura komentáře dokumentace XML. Při kompilaci můžete generovat soubor XML, který obsahuje dokumentační komentáře. Soubor XML generované kompilátorem lze distribuovat souběžně s vaší sestavení .NET, tak, aby Visual Studio a dalších integrovaného vývojového prostředí pomocí technologie IntelliSense můžete zobrazit rychlé informace o typy a členy. Kromě toho lze spustit soubor XML prostřednictvím nástrojů, například [DocFX](https://dotnet.github.io/docfx/) a [aplikaci Sandcastle](https://www.microsoft.com/download/details.aspx?id=10526) ke generování weby referenční dokumentace rozhraní API.

> [!NOTE]
> **Vložit komentář** příkaz, který automaticky vloží dokumentační komentáře XML je k dispozici v [C#](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments) a [jazyka Visual Basic](/dotnet/visual-basic/programming-guide/program-structure/how-to-create-xml-documentation). Však můžete ručně vložit [dokumentační komentáře XML v jazyce C++](/cpp/ide/xml-documentation-visual-cpp) soubory a stále generování souborů dokumentace XML v době kompilace.

## <a name="to-insert-xml-comments-for-a-code-element"></a>Chcete-li vložit komentáře XML pro element kódu

1. Umístěte kurzor text nad elementem chcete dokumentů, například metodu.

1. Proveďte jednu z těchto akcí:

   - Typ `///` v jazyce C# nebo `'''` v jazyce Visual Basic

   - Z **upravit** nabídce zvolte **IntelliSense** > **Vložit komentář**

   - Z klikněte pravým tlačítkem nebo kontextové nabídky na nebo nad tento element kódu, zvolte **fragment kódu** > **Vložit komentář**

   Šablona XML je vytvořena okamžitě výše element kódu. Například při psaní komentářů metodu, vygeneruje **\<souhrnné\>** elementu **\<param\>** element pro každý parametr a **\<vrátí\>** element dokumentu návratovou hodnotu.

   ![Šablona komentáře XML - C#](media/doc-preview-cs.png)

   ![Šablona komentáře XML - jazyka Visual Basic](media/doc-preview-vb.png)

1. Zadejte popis pro každý plně dokumentovat code element – element XML.

   ![Dokončené komentář](media/doc-result-cs.png)

> [!NOTE]
> Došlo [možnost](../../ide/reference/options-text-editor-csharp-advanced.md) pro dokumentační komentáře XML přepnutí po zadání `///` v jazyce C# nebo `'''` jazyka Visual Basic. V řádku nabídek zvolte **nástroje** > **možnosti** otevřete **možnosti** dialogové okno. Potom přejděte na **textového editoru** > **C#** nebo **základní** > **Upřesnit**. V **nápovědy k editoru** část, vyhledejte **dokumentační komentáře XML vygenerovat** možnost.

## <a name="see-also"></a>Viz také

[Dokumentační komentáře XML (C# Průvodce programováním)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)  
[Dokumentace kódu s XML – komentáře (Průvodce C#)](/dotnet/csharp/codedoc)  
[Postupy: vytvoření dokumentace XML (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/how-to-create-xml-documentation)  
[Komentáře v jazyce C++](/cpp/cpp/comments-cpp)  
[Dokumentace XML (C++)](/cpp/ide/xml-documentation-visual-cpp)  
[Generování kódu](../code-generation-in-visual-studio.md)
