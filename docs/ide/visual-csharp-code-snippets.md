---
title: Fragmenty kódu v C#
ms.date: 06/05/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- snippets [C#]
- code snippets [C#]
- Code Snippet Inserter [C#]
- C#, code snippets
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 6d96d547c3558c9c1e5ce4d11904a0c8cce048e7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="c-code-snippets"></a>Fragmenty kódu v C#

Fragmenty kódu jsou předem vytvořené fragmenty kódu, které lze rychle vložit do vašeho kódu. Například `for` fragment kódu vytvoří prázdnou `for` smyčky. Některé fragmenty kódu jsou obklopit fragmenty kódu, které vám umožní vybrat řádky kódu a potom vyberte fragment kódu, který zahrnuje vybrané řádky kódu. Například když vyberete řádků kódu a poté znovu aktivovat `for` fragment kódu, vytvoří `for` smyčky pomocí tyto řádky kódu uvnitř bloku smyčky. Fragmenty kódu můžete nastavit program psaní kódu rychlejší, jednodušší a spolehlivější.

 Můžete vložit fragment kódu v umístění kurzoru nebo vložit fragmentu kódu obklopit kolem aktuálně vybraný úsek kódu. Vkládací modul fragmentu kódu je vyvolána prostřednictvím **Vložit fragment kódu** nebo **příkazu Obklopit s** příkazy **IntelliSense** nabídky, nebo pomocí klávesové zkratky  **CTRL**+**tisíc**,**X** nebo **Ctrl**+**tisíc**,**S** v uvedeném pořadí.

 Vkládací modul fragmentu kódu zobrazuje název fragmentu kódu pro všechny fragmenty kódu k dispozici. Vkládací modul fragmentu kódu také zahrnuje vstupní dialogové okno zadává název fragmentu kódu nebo část názvu fragmentu kódu. Vkládací modul fragmentu kódu označuje nejvíce odpovídá název fragmentu kódu. Stisknutím **kartě** kdykoli bude zavřít Vkládací modul fragmentu kódu a vkládání aktuálně vybraný fragment kódu. Stisknutím **Esc** nebo kliknutím na tlačítko myši v editoru kódu se zavřít Vkládací modul fragmentu kódu bez vložení fragmentu kódu.

## <a name="default-code-snippets"></a>Výchozí fragmenty kódu

Ve výchozím nastavení jsou zahrnuty následující fragmenty kódu v sadě Visual Studio pro jazyk C#.

|Název (nebo místní)|Popis|Platná umístění vložit fragment kódu|
|--------------------------|-----------------|---------------------------------------|
|#if – direktiva|Vytvoří [#if](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-if) – direktiva a [#endif](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-endif) – direktiva.|Kdekoli.|
|#region – direktiva|Vytvoří [#region](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-region) – direktiva a [#endregion](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-endregion) – direktiva.|Kdekoli.|
|~|Vytvoří [finalizační metodu](/dotnet/csharp/programming-guide/classes-and-structs/destructors) (destruktor) pro obsahující třídu.|Uvnitř třídy.|
|– atribut|Vytvoří deklaraci pro třídu, která pochází z <xref:System.Attribute>.|V oboru názvů (včetně globálního oboru názvů), třídu nebo struktury.|
|checked|Vytvoří [zaškrtnutí](/dotnet/csharp/language-reference/keywords/checked) bloku.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|třída|Vytvoří deklaraci třídy.|V oboru názvů (včetně globálního oboru názvů), třídu nebo struktury.|
|konstruktoru|Vytvoří konstruktor pro obsahující třídu.|Uvnitř třídy.|
|SH|Vytvoří volání <xref:System.Console.WriteLine%2A>.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|do|Vytvoří [provést](/dotnet/csharp/language-reference/keywords/do) `while` smyčky.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|else|Vytvoří [else](/dotnet/csharp/language-reference/keywords/if-else) bloku.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|enum|Vytvoří [výčtu](/dotnet/csharp/language-reference/keywords/enum) deklarace.|V oboru názvů (včetně globálního oboru názvů), třídu nebo struktury.|
|equals|Vytvoří deklaraci metody, který přepíše <xref:System.Object.Equals%2A> metoda definované v <xref:System.Object> třídy.|Uvnitř třídy nebo struktury.|
|Výjimka|Vytvoří deklaraci pro třídu, která pochází z výjimku (<xref:System.Exception> ve výchozím nastavení).|V oboru názvů (včetně globálního oboru názvů), třídu nebo struktury.|
|pro|Vytvoří [pro](/dotnet/csharp/language-reference/keywords/for) smyčky.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|foreach|Vytvoří [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) smyčky.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|forr|Vytvoří [pro](/dotnet/csharp/language-reference/keywords/for) cykly této snižuje proměnnou smyčky po každé iteraci.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|if|Vytvoří [Pokud](/dotnet/csharp/language-reference/keywords/if-else) bloku.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|indexer|Vytvoří deklarace indexer.|Uvnitř třídy nebo struktury.|
|rozhraní|Vytvoří [rozhraní](/dotnet/csharp/language-reference/keywords/interface) deklarace.|V oboru názvů (včetně globálního oboru názvů), třídu nebo struktury.|
|Vyvolání|Vytvoří blok bezpečně vyvolá událost.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|iterátor|Vytvoří iterace.|Uvnitř třídy nebo struktury.|
|iterindex|Vytvoří pár "s názvem" iterator a indexer pomocí vnořené třídy.|Uvnitř třídy nebo struktury.|
|lock|Vytvoří [zámku](/dotnet/csharp/language-reference/keywords/lock-statement) bloku.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|mbox|Vytvoří volání <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName>. Možná budete muset přidat odkaz na System.Windows.Forms.dll.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|– obor názvů|Vytvoří [obor názvů](/dotnet/csharp/language-reference/keywords/namespace) deklarace.|Uvnitř oboru názvů (včetně globálního oboru názvů).|
|Prop|Vytvoří [automaticky implementované vlastnosti](/dotnet/csharp/programming-guide/classes-and-structs/auto-implemented-properties) deklarace.|Uvnitř třídy nebo struktury.|
|propfull|Vytvoří deklarace vlastnosti se `get` a `set` přistupující objekty.|Uvnitř třídy nebo struktury.|
|propg|Vytvoří jen pro čtení [automaticky implementované vlastnosti](/dotnet/csharp/programming-guide/classes-and-structs/auto-implemented-properties) s privátního `set` přistupujícího objektu.|Uvnitř třídy nebo struktury.|
|Správce bitových kopií|Vytvoří [statické](/dotnet/csharp/language-reference/keywords/static) [int](/dotnet/csharp/language-reference/keywords/int) hlavní metoda deklarace.|Uvnitř třídy nebo struktury.|
|struct |Vytvoří [struktura](/dotnet/csharp/language-reference/keywords/struct) deklarace.|V oboru názvů (včetně globálního oboru názvů), třídu nebo struktury.|
|svm|Vytvoří [statické](/dotnet/csharp/language-reference/keywords/static) [void](/dotnet/csharp/language-reference/keywords/void) hlavní metoda deklarace.|Uvnitř třídy nebo struktury.|
|– přepínač|Vytvoří [přepínač](/dotnet/csharp/language-reference/keywords/switch) bloku.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|Zkuste|Vytvoří [try-catch –](/dotnet/csharp/language-reference/keywords/try-catch) bloku.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|tryf|Vytvoří [try-finally –](/dotnet/csharp/language-reference/keywords/try-finally) bloku.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|unchecked|Vytvoří [nezaškrtnuté](/dotnet/csharp/language-reference/keywords/unchecked) bloku.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|unsafe|Vytvoří [unsafe](/dotnet/csharp/language-reference/keywords/unsafe) bloku.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|používání|Vytvoří [pomocí](/dotnet/csharp/language-reference/keywords/using-directive) – direktiva.|Uvnitř oboru názvů (včetně globálního oboru názvů).|
|while|Vytvoří [při](/dotnet/csharp/language-reference/keywords/while) smyčky.|Uvnitř metody indexer, přistupujícího objektu vlastnosti nebo přístupového objektu události.|

## <a name="see-also"></a>Viz také

- [Funkce fragmentu kódu](../ide/code-snippet-functions.md)
- [Fragmenty kódu](../ide/code-snippets.md)
- [Parametry šablony](../ide/template-parameters.md)
- [Postupy: Použití příkazu Obklopit s fragmenty kódu](../ide/how-to-use-surround-with-code-snippets.md)