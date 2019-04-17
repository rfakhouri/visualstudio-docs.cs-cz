---
title: Rozšířené možnosti, textový Editor, Basic (VB)
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Visual_Basic.Editor
- VS.ToolsOptionsPages.Text_Editor.Basic.Editor
- VS.ToolsOptionsPages.Visual_Basic_Editor.Editor
- VS.ToolsOptionsPages.Text_Editor.Basic.SimplifiedEditorPage
- VS.ToolsOptionsPages.Text_Editor.Basic
- VS.ToolsOptionsPages.Text_Editor.Basic.Advanced
- VS.ToolsOptionsPages.Text_Editor.Basic.VB_Specific
helpviewer_keywords:
- Basic Text Editor Options dialog box
ms.assetid: 5a8cafca-f7b4-4a2d-92ce-6894a7673d00
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 60ef24f91d7b450de4ed4779a6d128032bd8b564
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59661695"
---
# <a name="options-text-editor-basic-visual-basic-advanced"></a>Rozšířené možnosti, textový Editor, Basic (Visual Basic)
**VB konkrétní** stránce vlastností **základní** složky **textový Editor** složky **možnosti** (**nástroje** nabídky) dialogové okno obsahuje následující vlastnosti:

## <a name="analysis"></a>Analýza

- Povolení úplné analýzy řešení

   Umožňuje analýzu kódu u všech souborů v řešení, ne jenom otevřít soubory kódu. Další informace najdete v tématu [úplné analýzy řešení](../../code-quality/how-to-enable-and-disable-full-solution-analysis-for-managed-code.md).

## <a name="using-directives"></a>Direktivy using

- Umístit nejdřív direktivy "System", při řazení direktiv Using

   Pokud je vybráno, **odebrat a seřadit direktivy using** příkaz v nabídce seřadí klikněte pravým tlačítkem `using` direktivy a místa obory názvů "Systém" v horní části seznamu.

- Oddělovat skupiny direktiv using

   Pokud je vybráno, **odebrat a seřadit direktivy using** odděluje příkazu v místní nabídce `using` direktivy vložením prázdný řádek mezi skupinami direktivy, které mají stejný obor názvů root.

- Navrhnout použití typů v sestaveních reference
- Navrhnout použití typů v balíčcích NuGet

   Když tyto možnosti jsou vybrané, [rychlá akce](../quick-actions.md) je k dispozici pro instalaci balíčku NuGet a přidejte `using` směrnice pro neodkazovaný typy.

   ![Rychlé akce pro instalaci balíčku NuGet v sadě Visual Studio](media/nuget-lightbulb.png)

## <a name="highlighting"></a>Zvýraznění

 **Povolit zvýrazňování odkazů a klíčových slov**

Do textového editoru můžete zvýraznit všechny výskyty symbolu nebo všechna klíčová slova v klauzuli například `If..Then`, `While...End While`, nebo `Try...Catch...Finally`. Mezi zvýrazněných odkazů nebo klíčová slova můžete přejít stisknutím klávesy **Ctrl** + **Shift** + **šipka dolů** nebo **Ctrl**   +  **Shift** + **šipka nahoru**.

## <a name="outlining"></a>Sbalování

**Povolení režimu sbalení**

Při otevření souboru v editoru kódu se zobrazí dokument v režimu sbalování. Zobrazit [Osnova](../../ide/outlining.md) Další informace. Pokud je vybraná tato možnost, funkci sbalování se aktivuje při otevření souboru.

**Zobrazit oddělovače řádků procedury**

Textový editor označuje visual oboru postupy. Řádek je vykreslen v *.vb* zdrojové soubory vašeho projektu v umístěních uvedených v následující tabulce:

|Umístění ve zdrojovém souboru .vb|Příklad umístění řádku|
|---------------------------------|------------------------------|
|Po uzavření bloku deklarace konstruktoru|– Na konci třída, struktura, modul, rozhraní nebo výčet<br />-After vlastnost, funkce nebo procedury sub<br />-Není mezi get a set klauzule ve vlastnosti|
|Po sadu konstrukce jeden řádek|-After příkazy pro import, před definici typu v souboru třídy<br />-After proměnné deklarované ve třídě, před všechny postupy|
|Po jeden řádek deklarací (deklarace mimo blok úrovně)|-Následující příkazy pro import, dědí příkazy deklarace proměnných, deklarace události, delegát deklarace a příkazy deklarovat knihovny DLL|

## <a name="block-structure-guides"></a>Vodítka pro strukturu bloku

Pokud je vybráno, svislé čáry zobrazí v editoru tento řádek nahoru strukturovaný kód bloky, které vám umožní snadno identifikovat jednotlivé bloky kódu. Například zobrazí čáry mezi `Sub` a `EndSub` v `Sub` příkazu.

## <a name="editor-help"></a>Nápověda k editoru

**Hezký výpis (přeformátování) kódu** přeformátuje textový editor kódu podle potřeby. Pokud je vybraná tato možnost, bude se editor kódu:

-   Zarovnat kód do umístění správné tabulátoru

-   Recase klíčová slova, proměnných a objektů na správnou velikost.

-   Přidat chybějící `Then` do `If...Then` – příkaz

-   Přidat závorky k volání funkce

-   Přidat chybí koncové uvozovky na řetězce

-   U vydavatelských exponenciální zápis

-   U vydavatelských kalendářních dat

**Automatické vkládání koncových konstruktorů**

Po zadání – například první řádek deklaraci procedury `Sub Main`– a stiskněte klávesu **Enter**, textový editor přidá odpovídající `End Sub` řádku. Podobně pokud chcete přidat [pro](/dotnet/visual-basic/language-reference/statements/for-next-statement) smyčky, textový editor přidá odpovídající `Next` příkazu. Pokud je vybraná tato možnost, editor kódu automaticky přidá koncová konstrukce.

**Automatické vložení členů rozhraní a MustOverride**

Pokud jste se zavázali `Implements` příkaz nebo `Inherits` příkaz pro třídu, textový editor vloží prototypy pro členy, které musí být implementován nebo jeho přepsána, v uvedeném pořadí.

**Povolit návrhy oprav**

Do textového editoru můžete navrhnout řešení pro běžné chyby a umožní vám vybrat příslušnou opravu se následně použije na váš kód.

## <a name="see-also"></a>Viz také:

- [Obecné, Prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)
- [Možnosti, Textový editor, Všechny jazyky, Tabulátory](../../ide/reference/options-text-editor-all-languages-tabs.md)
