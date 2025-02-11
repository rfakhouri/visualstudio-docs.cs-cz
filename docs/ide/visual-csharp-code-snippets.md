---
title: C#fragmenty kódu
ms.date: 06/05/2017
ms.topic: reference
helpviewer_keywords:
- snippets [C#]
- code snippets [C#]
- Code Snippet Inserter [C#]
- C#, code snippets
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 7a785623ea36fe25833f24f760c29f49ca40b459
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68918671"
---
# <a name="c-code-snippets"></a>C#fragmenty kódu

Fragmenty kódu jsou předem připravené fragmenty kódu, které můžete rychle vložit do kódu. Například `for` fragment kódu vytvoří prázdnou `for` smyčku. Některé fragmenty kódu jsou obklopeny – s fragmenty kódu, které umožňují vybrat řádky kódu a pak vybrat fragment kódu, který zahrnuje vybrané řádky kódu. Například když vyberete řádky kódu a pak aktivujete `for` fragment kódu, `for` vytvoří smyčku s těmito řádky kódu uvnitř bloku smyčky. Fragmenty kódu můžou urychlit psaní kódu programu, jednodušší a spolehlivější.

Fragment kódu můžete vložit do umístění kurzoru nebo vložit obklopit s fragmentem kódu kolem aktuálně vybraného kódu. Fragment kódu Inserter je vyvolán prostřednictvím příkazu **Vložit fragment kódu** nebo obklopit příkazy v nabídce **technologie IntelliSense** nebo pomocí klávesových zkratek **CTRL**+**K**,**X** nebo **CTRL** .+ **K**, v.

**Fragment kódu Inserter** zobrazí název fragmentu kódu pro všechny dostupné fragmenty kódu. Fragment kódu Inserter také obsahuje vstupní dialogové okno, kde můžete zadat název fragmentu kódu nebo část názvu fragmentu kódu. Fragment kódu Inserter zvýrazňuje nejbližší shodu s názvem fragmentu kódu. Stiskem klávesy **TAB** kdykoliv dojde k zavření fragmentu kódu Inserter a vložení aktuálně vybraného fragmentu kódu. Stisknutím klávesy **ESC** nebo kliknutím na myš v editoru kódu zavřete fragment kódu Inserter bez vložení fragmentu kódu.

## <a name="default-code-snippets"></a>Výchozí fragmenty kódu

Ve výchozím nastavení jsou součástí sady Visual Studio pro C#aplikaci následující fragmenty kódu.

|Název (nebo zástupce)|Popis|Platná umístění pro vložení fragmentu|
| - |-----------------| - |
|#if – direktiva|Vytvoří direktivu [#if](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-if) a direktivu [#endif](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-endif) .|Jakékoli.|
|#region – direktiva|Vytvoří direktivu [#region](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-region) a direktivu [#endregion](/dotnet/csharp/language-reference/preprocessor-directives/preprocessor-endregion) .|Jakékoli.|
|~|Vytvoří [finalizační metodu](/dotnet/csharp/programming-guide/classes-and-structs/destructors) (destruktor) pro třídu, která ji obsahuje.|Uvnitř třídy.|
|– atribut|Vytvoří deklaraci pro třídu, která je odvozena <xref:System.Attribute>z.|V oboru názvů (včetně globálního oboru názvů), třídy nebo struktury.|
|checked|Vytvoří [kontrolovaný](/dotnet/csharp/language-reference/keywords/checked) blok.|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|třída|Vytvoří deklaraci třídy.|V oboru názvů (včetně globálního oboru názvů), třídy nebo struktury.|
|ctor|Vytvoří konstruktor pro třídu, která ji obsahuje.|Uvnitř třídy.|
|cw|Vytvoří volání <xref:System.Console.WriteLine%2A>.|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|do|Vytvoří smyčku do. [](/dotnet/csharp/language-reference/keywords/do) `while`|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|else|Vytvoří blok [Else](/dotnet/csharp/language-reference/keywords/if-else) .|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|enum|Vytvoří deklaraci [výčtu](/dotnet/csharp/language-reference/keywords/enum) .|V oboru názvů (včetně globálního oboru názvů), třídy nebo struktury.|
|equals|Vytvoří deklaraci metody, která přepíše <xref:System.Object.Equals%2A> metodu definovanou <xref:System.Object> ve třídě.|Uvnitř třídy nebo struktury.|
|jímka|Vytvoří deklaraci pro třídu, která je odvozena z výjimky (<xref:System.Exception> ve výchozím nastavení).|V oboru názvů (včetně globálního oboru názvů), třídy nebo struktury.|
|pro|Vytvoří smyčku [for](/dotnet/csharp/language-reference/keywords/for) .|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|foreach|Vytvoří smyčku [foreach](/dotnet/csharp/language-reference/keywords/foreach-in) .|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|forr|Vytvoří smyčku [for](/dotnet/csharp/language-reference/keywords/for) , která po každé iteraci sníží proměnnou smyčky.|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|if|Vytvoří blok [if](/dotnet/csharp/language-reference/keywords/if-else) .|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|indexer|Vytvoří deklaraci indexeru.|Uvnitř třídy nebo struktury.|
|rozhraní|Vytvoří deklaraci [rozhraní](/dotnet/csharp/language-reference/keywords/interface) .|V oboru názvů (včetně globálního oboru názvů), třídy nebo struktury.|
|Zavolejte|Vytvoří blok, který bezpečně vyvolá událost.|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|iterátor|Vytvoří iterátor.|Uvnitř třídy nebo struktury.|
|iterindex|Vytvoří iterátor "pojmenovaný" a dvojici indexeru pomocí vnořené třídy.|Uvnitř třídy nebo struktury.|
|lock|Vytvoří blok [zámku](/dotnet/csharp/language-reference/keywords/lock-statement) .|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|mbox|Vytvoří volání <xref:System.Windows.Forms.MessageBox.Show%2A?displayProperty=fullName>. Je možné, že budete muset přidat odkaz na *System. Windows. Forms. dll*.|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|– obor názvů|Vytvoří deklaraci [oboru názvů](/dotnet/csharp/language-reference/keywords/namespace) .|Uvnitř oboru názvů (včetně globálního oboru názvů).|
|Úprava|Vytvoří deklaraci [automaticky implementované vlastnosti](/dotnet/csharp/programming-guide/classes-and-structs/auto-implemented-properties) .|Uvnitř třídy nebo struktury.|
|propfull|Vytvoří deklaraci vlastnosti s `get` přístupovými objekty a `set` .|Uvnitř třídy nebo struktury.|
|propg|Vytvoří [automaticky implementovanou vlastnost](/dotnet/csharp/programming-guide/classes-and-structs/auto-implemented-properties) , která je určena jen pro čtení, `set` pomocí privátního přístupového objektu.|Uvnitř třídy nebo struktury.|
|Instalační|Vytvoří [statickou](/dotnet/csharp/language-reference/keywords/static) deklaraci hlavní metody [int](/dotnet/csharp/language-reference/keywords/int) .|Uvnitř třídy nebo struktury.|
|struct|Vytvoří deklaraci [struktury](/dotnet/csharp/language-reference/keywords/struct) .|V oboru názvů (včetně globálního oboru názvů), třídy nebo struktury.|
|svm|Vytvoří [statickou](/dotnet/csharp/language-reference/keywords/static) deklaraci hlavní metody [void](/dotnet/csharp/language-reference/keywords/void) .|Uvnitř třídy nebo struktury.|
|– přepínač|Vytvoří blok [přepínače](/dotnet/csharp/language-reference/keywords/switch) .|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|Zkuste|Vytvoří blok [try-catch](/dotnet/csharp/language-reference/keywords/try-catch) .|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|tryf|Vytvoří blok [try-finally](/dotnet/csharp/language-reference/keywords/try-finally) .|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|unchecked|Vytvoří nekontrolované bloky. [](/dotnet/csharp/language-reference/keywords/unchecked)|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|unsafe|Vytvoří [nebezpečný](/dotnet/csharp/language-reference/keywords/unsafe) blok.|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|
|používání|Vytvoří direktivu [using](/dotnet/csharp/language-reference/keywords/using-directive) .|Uvnitř oboru názvů (včetně globálního oboru názvů).|
|while|Vytvoří smyčku [while](/dotnet/csharp/language-reference/keywords/while) .|Uvnitř metody, indexeru, přistupujícího objektu vlastnosti nebo přístupového objektu události.|

## <a name="see-also"></a>Viz také:

- [Funkce fragmentu kódu](../ide/code-snippet-functions.md)
- [Fragmenty kódu](../ide/code-snippets.md)
- [Parametry šablony](../ide/template-parameters.md)
- [Postupy: Použití příkazu obklopit s fragmenty kódu](../ide/how-to-use-surround-with-code-snippets.md)