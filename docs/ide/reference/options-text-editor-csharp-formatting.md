---
title: C# editor možnosti formátování
ms.date: 08/14/2018
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.Spacing
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.NewLines
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.Indentation
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.Wrapping
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting
- VS.ToolsOptionsPages.Text_Editor.CSharp.Formatting.General
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.Formatting.General
helpviewer_keywords:
- formatting options [C#]
- Text editor Options dialog box, formatting
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: a11fa7913828ef557c87ec50184c9de35a9e5bc4
ms.sourcegitcommit: 2ee11676af4f3fc5729934d52541e9871fb43ee9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2019
ms.locfileid: "65847434"
---
# <a name="options-dialog-box-text-editor--c--code-style--formatting"></a>Dialogové okno Možnosti: Textový Editor \> C# \> styl kódu \> formátování

Použití **formátování** možnosti stránky a jeho podstránky ([**odsazení**](#indentation-page), **nové řádky**, **mezery** a **obtékání**) Chcete-li nastavit možnosti formátování kódu v editoru kódu.

Chcete-li získat přístup k této stránce Možnosti, zvolte **nástroje** > **možnosti** z řádku nabídek. V **možnosti** dialogového okna zvolte **textový Editor** > **jazyka C#** > **styl kódu**  >  **Formátování**.

> [!TIP]
> **Odsazení**, **nové řádky**, **mezery**, a **obtékání** podstránky každý zobrazit okno náhledu v dolní části, který ukazuje účinky jednotlivých možností. Pokud chcete použít okno náhledu, vyberte možnost formátování. Okno náhledu ukazuje příklad vybrané možnosti. Pokud změníte nastavení tak, že vyberete tlačítko přepínače nebo zaškrtávacího políčka, okno náhledu se aktualizuje a zobrazí vliv nové nastavení.

## <a name="formatting-general-page"></a>Formátování stránky (Obecné)

### <a name="general-settings"></a>Obecná nastavení

Tato nastavení ovlivňují *při* editoru kódu se týká možnosti formátování kódu.

|Popisek|Popis|
|-----------|-----------------|
|**Automaticky formátovat při psaní**|Když vybraná, **formátovat příkaz při;** a **formátovat blok při}** je zakázaná.|
|**Automaticky formátu příkaz při;**|Pokud je vybráno, formátuje příkazy po dokončení podle možnosti formátování pro editor vybrané.|
|**Automaticky formátovat blok při}**|Pokud je vybráno, formáty bloky podle vybrané editoru co nejdříve po dokončení bloku kódu možnosti formátování kódu.|
|**Automaticky formátovat při vrácení**|Pokud je vybráno, formátuje text při **Enter** stisknutí podle možnosti formátování pro editor vybrané.|
|**Automaticky formátovat při vložení**|Pokud je vybráno, formátuje text, který je vložen do editoru podle možnosti formátování pro editor vybrané.|

::: moniker range="vs-2019"

Pokud jste dříve použili nastavení stylu kódu pro C# soubory použijte **formátovat dokument** příkaz v sadě Visual Studio 2017, která je teď dostupná jako funkce [ **vyčištění kódu** ](../code-styles-and-code-cleanup.md#apply-code-styles).

::: moniker-end

::: moniker range="vs-2017"

### <a name="format-document-settings"></a>Formát dokumentu nastavení

Tato nastavení konfigurují **formátovat dokument** příkazu, vyčistěte další kód v souboru. Další informace o tom, jak tato nastavení se použijí, naleznete v tématu [příkazu formát dokumentu](../code-styles-and-code-cleanup.md#apply-code-styles).

|Popisek|Popis|Odpovídající EditorConfig a nástroje > Možnosti pravidla|
|-----------|-----------------|-----------------|-----------------|
|**Použít všechny jazyka C# formátování pravidla (odsazení, zabalení, mezery)**|**Formátovat dokument** příkaz vždy opravy formátování problémy. Toto nastavení nedá změnit.| [EditorConfig jádra](../../ide/create-portable-custom-editor-options.md)<br/>[Možnosti formátování pro .NET EditorConfig](../../ide/editorconfig-code-style-settings-reference.md#formatting-conventions)<br/><br/>**Nástroje** > **možnosti** > **textový Editor**  >  **C#**  >   **Formátování** > [**odsazení** nebo **nové řádky** nebo **mezery** nebo **obtékání**]|
|**Během formátování provést čištění přidání kódu**|Pokud je vybráno, platí opravy pro níže uvedené na pravidla **Edit.FormatDocument** příkazu.| Není k dispozici |
|**Odebrat nepotřebné direktivy using**|Pokud je vybráno, odstraní nepotřebné `using` direktivy při **Edit.FormatDocument** se aktivuje.| Není k dispozici |
|**Řazení direktiv Using**|Pokud je vybráno, seřadí `using` direktivy při **Edit.FormatDocument** se aktivuje.| dotnet_sort_system_directives_first<br/><br/>**Nástroje** > **možnosti** > **textový Editor** > **jazyka C#** > **Advanced**   >  **Místo "Systém" direktivy první při řazení direktiv Using** |
|**Přidání nebo odebrání složených závorek pro jeden řádek řídicí příkazy**|Když vyberete, přidá nebo odebere složené závorky jedním řádkem řídicí příkazy při **Edit.FormatDocument** se aktivuje.| csharp_prefer_braces<br/><br/>**Nástroje** > **možnosti** > **textový Editor** > **jazyka C#** > **styl kódu**   >  **Předvolby bloku kódu** > **preferovat složené závorky** |
|**Přidat modifikátory dostupnosti.**|Když vyberete, přidá chybějící modifikátory dostupnosti. Pokud **Edit.FormatDocument** se aktivuje.| dotnet_style_require_accessibility_modifiers |
|**Seřadit modifikátory**|Pokud je vybráno, seřadí modifikátory při **Edit.FormatDocument** se aktivuje.| csharp_preferred_modifier_order<br/>visual_basic_preferred_modifier_order |
|**Použití předvolby tělo výrazu/blokování**|Pokud je vybráno, převede členové tvoření blokování subjekty, nebo naopak, když **Edit.FormatDocument** se aktivuje.| [Možnosti s výrazem v těle členské EditorConfig](../../ide/editorconfig-code-style-settings-reference.md#expression_bodied_members)<br/><br/>**Nástroje** > **možnosti** > **textový Editor** > **jazyka C#** > **styl kódu**   >  **Předvolby výrazu** > **používat text výrazu pro metody, konstruktory, atd.** |
|**Použít implicitní nebo explicitní typ předvolby**|Pokud je vybráno, převede `var` na explicitní typ nebo naopak, když **Edit.FormatDocument** se aktivuje.| [EditorConfig možnosti explicitní typ](../../ide/editorconfig-code-style-settings-reference.md#implicit-and-explicit-types)<br/><br/>**Nástroje** > **možnosti** > **textový Editor** > **jazyka C#** > **styl kódu**   >  **předvolby pro "var"** |
|**Použití vložených proměnných předvoleb out**|Pokud je vybráno, inlines `out` proměnné kde je to možné v případě **Edit.FormatDocument** se aktivuje.| csharp_style_inlined_variable_declaration<br/><br/>**Nástroje** > **možnosti** > **textový Editor** > **jazyka C#** > **styl kódu**   >  **Proměnné předvoleb** > **upřednostňovat vloženou deklaraci proměnných** |
|**Použít jazyk a rozhraní typ předvolby**|Pokud je vybráno, převede jazyk typy na typy rozhraní framework, nebo naopak, když **Edit.FormatDocument** se aktivuje.| dotnet_style_predefined_type_for_locals_parameters_members<br/>dotnet_style_predefined_type_for_member_access<br/><br/>**Nástroje** > **možnosti** > **textový Editor** > **jazyka C#** > **styl kódu**   >  **předdefinované předvolby typů** |
|**Použití předvoleb inicializace objektu nebo kolekce**|Pokud je vybráno, používá inicializátory objektu a kolekce, kde je to možné při **Edit.FormatDocument** se aktivuje.| dotnet_style_object_initializer<br/>dotnet_style_collection_initializer<br/><br/>**Nástroje** > **možnosti** > **textový Editor** > **jazyka C#** > **styl kódu**   >  **Předvolby výrazu** > **upřednostňovat inicializátor objektu** nebo **upřednostňovat inicializátor kolekce** |
|**Použití "this." kvalifikační předvolby**|Pokud je vybráno, platí `this.` předvolby při **Edit.FormatDocument** se aktivuje.| [Tento. EditorConfig možnosti kvalifikace](../../ide/editorconfig-code-style-settings-reference.md#this_and_me)<br/><br/>**Nástroje** > **možnosti** > **textový Editor** > **jazyka C#** > **styl kódu**   >  **předvolby 'this'.** |
|**Ujistěte se, jen pro čtení privátní pole, pokud je to možné**|Při výběru, umožňuje privátní pole `readonly` kde je to možné v případě **Edit.FormatDocument** se aktivuje.| dotnet_style_readonly_field<br/><br/>**Nástroje** > **možnosti** > **textový Editor** > **jazyka C#** > **styl kódu**   >  **Pole Předvolby** > **preferovat jen pro čtení** |
|**Odebrat nepotřebné přetypování**|Při výběru, odstraní nepotřebné přetypování, kde je to možné při **Edit.FormatDocument** se aktivuje.| Není k dispozici |
|**Odebrat nepoužité proměnné**|Pokud je vybráno, odebere proměnné, které nejsou používány, při **Edit.FormatDocument** se aktivuje.| Není k dispozici |

![Nastavení vyčištění kódu pro jazyk C# v sadě Visual Studio](media/format-document-settings.png)

::: moniker-end

## <a name="indentation-page"></a>Stránka odsazení

Odsazení možnosti na této stránce se projeví, když je kód automaticky formátován. Jedna je například když je kód automaticky formátován po vložení kódu do souboru při **automaticky formátovat při vložení** zaškrtnuto. ( **Automaticky formátovat při vložení** možnost je v části **formátování** > **Obecné**.)

![C#Možnosti odsazení textového editoru v sadě Visual Studio](media/csharp-indentation-options.png)

> [!TIP]
> Existují také možnosti odsazení na **textový Editor** > **C#** > **karty** stránka možností. Tyto možnosti jenom určit, kde editoru kódu umístí kurzor po stisknutí klávesy **Enter** na konci řádku.
>
> ![C#textový editor přehled možností v sadě Visual Studio](media/csharp-tabs-options.png)

## <a name="see-also"></a>Viz také:

- [Obecné, prostředí, dialogové okno Možnosti](../../ide/reference/general-environment-options-dialog-box.md)