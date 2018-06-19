---
title: Možnosti, textový editor, Basic (Visual Basic)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Visual_Basic.Editor
- VS.ToolsOptionsPages.Text_Editor.Basic.Editor
- VS.ToolsOptionsPages.Visual_Basic_Editor.Editor
- VS.ToolsOptionsPages.Text_Editor.Basic.SimplifiedEditorPage
- VS.ToolsOptionsPages.Text_Editor.Basic
- VS.ToolsOptionsPages.Text_Editor.Basic.VB_Specific
helpviewer_keywords:
- Basic Text Editor Options dialog box
ms.assetid: 5a8cafca-f7b4-4a2d-92ce-6894a7673d00
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 27048b5d70674cd492227e96682f8401ed7160ee
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31945854"
---
# <a name="options-text-editor-basic-visual-basic"></a>Možnosti, textový editor, Basic (Visual Basic)
**VB konkrétní** stránka Vlastnosti, **základní** složky **textového editoru** složky **možnosti** (**nástroje** nabídky) dialogové okno obsahuje následující vlastnosti:

 **Automatické vkládání end konstrukce** při zadávání – například první řádek deklaraci postup `Sub Main—`a stiskněte klávesu ENTER, textový editor přidá odpovídající `End Sub` řádku. Podobně pokud přidáte [pro](/dotnet/visual-basic/language-reference/statements/for-next-statement) ve smyčce, textový editor přidá odpovídající `Next` příkaz. Pokud je vybraná tato možnost, editoru kódu automaticky přidá konstrukce end.

 **Poměrně výpis (přeformátování) kódu** textový editor přeformátuje kódu podle potřeby. Pokud je vybraná tato možnost, bude editoru kódu:

-   Zarovnat kódu do polohy správný karta

-   Recase klíčová slova, proměnné a objekty, které se správnou velikost

-   Přidejte chybějící `Then` k `If...Then` – příkaz

-   Přidat závorky k volání funkcí

-   Přidejte chybějící koncové uvozovky na řetězce

-   Přeformátujte exponenciální zápis

-   Přeformátujte kalendářních dat

**Povolit režim osnovy**

Při otevření souboru v editoru kódu, můžete zobrazit dokumentu v osnovy režimu. V tématu [Osnova](../../ide/outlining.md) Další informace. Pokud je vybraná tato možnost, popisující funkce je aktivovaná, při otevření souboru.

**Automatické vkládání rozhraní a MustOverride členů**

Když potvrdíte `Implements` příkaz nebo `Inherits` příkaz pro třídu, textový editor vloží prototypy pro členy, které musí být implementován nebo jeho přepsána, v uvedeném pořadí.

**Zobrazit postup čáry oddělovače**

Textový editor označuje visual rozsah procedury. Řádek se vykresluje v VB zdrojové soubory vašeho projektu v umístěních uvedených v následující tabulce:

|Umístění v VB zdrojový soubor|Příklad umístění řádku|
|---------------------------------|------------------------------|
|Po ukončení konstrukce deklarace bloku|-Na konci třídy, struktury, modulu, rozhraní nebo výčtu<br />– Po vlastnost, function nebo sub<br />-Není mezi get a set klauzule ve vlastnosti|
|Po sadu jeden řádek konstrukce|– Po importu příkazy, než v souboru – třída definice typu<br />– Po proměnné deklarovaná ve třídě, než všechny postupy|
|Po jeden řádek deklarace (bez bloku úrovně deklarace)|-Následující příkazy pro import, dědí příkazy, proměnné deklarace, deklarace událostí, delegát deklarace a knihovny DLL deklarovat příkazy|

**Povolit návrhy korekce chyb**

Textového editoru můžete navrhnout řešení běžných chyb a pro výběr na požadovanou opravu, které se pak použije k vašeho kódu.

**Povolit zvýraznění odkazy a klíčová slova**

Textového editoru můžete zvýrazněte všechny instance symbol nebo všech klíčových slov v klauzuli například `If..Then`, `While...End While`, nebo `Try...Catch...Finally`. Stisknutím kombinace kláves CTRL + SHIFT + šipka dolů nebo CTRL + SHIFT + šipka nahoru mohou procházet mezi zvýrazněné odkazy nebo klíčová slova.

## <a name="see-also"></a>Viz také

- [Obecné, prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)
- [Možnosti, textový Editor, všechny jazyky, karty](../../ide/reference/options-text-editor-all-languages-tabs.md)