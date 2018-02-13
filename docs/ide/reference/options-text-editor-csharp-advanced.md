---
title: "Možnosti, textový Editor, C#, Upřesnit | Microsoft Docs"
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Outlining
- VS.ToolsOptionsPages.Text_Editor.CSharp.Advanced
helpviewer_keywords:
- XML comments
- XML documentation, generating
- outlining options [C#]
- XML documentation, creating
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- dotnet
ms.openlocfilehash: 5d6cf8b655151e9b07111b6ac6fd64b6ad3c845f
ms.sourcegitcommit: 238cd48787391aa0ed1eb684f3f04e80f7958705
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/12/2018
---
# <a name="options-text-editor-c-advanced"></a>Možnosti, textový editor, C#, upřesnit

Použití **Upřesnit** stránka Možnosti, chcete-li změnit nastavení pro editor formátování, kódu refaktoringu a dokumentační komentáře XML pro jazyk C#. Chcete-li získat přístup k této stránce Možnosti, zvolte **nástroje** > **možnosti**a potom vyberte **textového editoru** > **C#**  >  **Rozšířené**.

> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md).

## <a name="analysis"></a>Analýza

- Povolit úplnou analýzu řešení

   Analýza kódu umožňuje u všech souborů v řešení, ne jenom otevřít soubory kódu. Další informace najdete v tématu [úplné analýzy řešení](../../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md).

- Provedení analýzy funkce editor v externího procesu (experimentální)

## <a name="using-directives"></a>Pomocí direktiv

- Nejprve umístit direktivy "Systém", pokud řazení direktiv Using

- Oddělit pomocí direktivy skupin

- Navrhněte direktiv using pro typy v referenční sestavení

- Navrhněte direktiv using pro typy v balíčků NuGet

## <a name="highlighting"></a>Zvýraznění

- Zvýrazněte odkazy na symbolů v místě kurzoru

   Když kurzor je nastavený uvnitř symbol, nebo když klikněte na symbol, jsou vyznačené všechny instance tohoto symbolu v souboru kódu.

- Zvýrazněte související klíčová slova v místě kurzoru

## <a name="outlining"></a>Sbalování

- Zadejte popisující režimu při otevírání souborů

   Při výběru automaticky přehled souboru kódu, který vytvoří sbalitelné bloky kódu. Při prvním otevření souboru #regions bloky a bloky kódu neaktivní sbalte.

- Zobrazit postup čáry oddělovače

- Zobrazení osnovy pro úrovně konstrukce deklarace

- Zobrazení osnovy pro úrovně konstrukce kódu

- Zobrazení osnovy pro komentáře a oblastí, preprocesoru

- Sbalit #regions při sbalení do definice

## <a name="fading"></a>Pozvolného vysouvání

- Vykreslit out nepoužitých direktiv Using

- Vykreslit out nedostupný kódu

## <a name="block-structure-guides"></a>Blokovat struktura příručky

- Zobrazit příručky pro úrovně konstrukce deklarace

- Zobrazit příručky pro úrovně konstrukce kódu

## <a name="editor-help"></a>Nápovědy k editoru

- Generovat dokumentační komentáře XML pro / / /

   Pokud vybraná, vloží elementy XML pro dokumentační komentáře XML po zadání `///` Úvod komentář. Další informace o dokumentace XML, najdete v části [dokumentační komentáře XML (C# Průvodce programováním)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments).

- Vložit \* na začátku nového řádku při zápisu nebo\* \*/ komentáře

- Zobrazit náhled pro přejmenování sledování

- Zadejte rozdělení textové literály v

- Sestavy neplatná zástupné symboly v ' řetězec. Formát ' volání

## <a name="extract-method"></a>extrahování metody

- Nepřidávejte put ref nebo out na vlastní – struktura

## <a name="implement-interface-or-abstract-class"></a>Implementace rozhraní nebo abstraktní třídy

- Při vkládání vlastnosti, události a metody, umístěte je s ostatními členy stejného druhu nebo na konci

- Při generování vlastnosti, raději vyvolání vlastnosti nebo vhodnější automaticky vlastnosti

## <a name="see-also"></a>Viz také

[Postupy: vložení komentáře XML pro dokumentaci generování](../../ide/reference/generate-xml-documentation-comments.md)  
[Dokumentační komentáře XML (C# Průvodce programováním)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)  
[Dokumentace kódu s XML – komentáře (Průvodce C#)](/dotnet/csharp/codedoc)  
[Nastavení možností editoru pro konkrétní jazyk](../../ide/reference/setting-language-specific-editor-options.md)  
[C# IntelliSense](../../ide/visual-csharp-intellisense.md)