---
title: Dialogové okno Upřesnit nastavení sestavení (C#)
ms.date: 06/20/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- cs.AdvancedBuildSettings
helpviewer_keywords:
- Build options [C#], advanced
ms.assetid: 141f2dee-1563-4ce6-ba37-32920b082519
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: dc9900927218e543b4e7ba962d7ea019d927c8a8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="advanced-build-settings-dialog-box-c"></a>Dialogové okno Upřesnit nastavení sestavení (C#)

Použití **Upřesnit nastavení sestavení** dialogové okno s **Návrhář projektu** k určení rozšířenou vlastností konfigurace sestavení projektu. Toto dialogové okno se vztahuje na [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] pouze projekty.

## <a name="general"></a>Obecné

 Následující možnosti vám umožňují nastavit obecné Upřesnit nastavení.

 **Jazyková verze** Určuje verzi jazyka. Sada funkcí se liší v jednotlivých verzích, tato možnost slouží k vynucení kompilátoru povolit pouze podmnožinu implementovanou funkcí nebo povolit pouze funkce kompatibilní s současných standardů. Toto nastavení má následující možnosti:

 - **default**

   Cílem aktuální verze.

- **ISO-1** a **ISO-2**

  Cílem standardní funkce ISO-1 a ISO 2, v uvedeném pořadí.

- **C# [číslo verze]**

 Cílí na konkrétní verzi jazyka C#. Další informace najdete v tématu [/langversion (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/langversion-compiler-option).


 **Interní hlášení chyb kompilátoru** Určuje, zda chcete společnosti Microsoft zasílat zprávy o chybách kompilátoru. Pokud nastavena na **řádku** (výchozí), se zobrazí se výzva Pokud dojde k chybě vnitřní kompilátoru, která poskytuje možnost elektronicky odešle zprávu o chybách společnosti Microsoft. Pokud nastavena na **odeslat**, zprávu o chybách automaticky odešle. Pokud nastavena na **fronty**, zprávy o chybách se zařadí do fronty. Pokud nastavena na **žádné**, ohlásí chybu pouze ve výstupu kompilátoru text. Další informace najdete v tématu [/errorreport (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/errorreport-compiler-option).

 **Kontrola aritmetického přetečení nebo podtečení** Určuje, zda celočíselný aritmetický příkaz, který není v oboru [zaškrtnutí](/dotnet/csharp/language-reference/keywords/checked) nebo [nezaškrtnuté](/dotnet/csharp/language-reference/keywords/unchecked) klíčová slova a že výsledkem je hodnota mimo rozsah dat typu způsobí výjimku za běhu. Další informace najdete v tématu [/ checked (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/checked-compiler-option).

 **Neodkazovat mscorlib.dll** Určuje, zda mscorlib.dll bude importována do programu, definování celý <xref:System> oboru názvů. Toto políčko zaškrtněte, pokud chcete definovat nebo vytvořit vlastní <xref:System> obor názvů a objekty. Další informace najdete v tématu [/nostdlib (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/nostdlib-compiler-option).

## <a name="output"></a>Výstup

 Následující možnosti vám umožňují určit možnosti pokročilé výstupu.

 **Informace o ladění** Určuje typ ladicí informace generované kompilátorem. Informace o tom, jak nakonfigurovat ladění výkonu aplikace, najdete v tématu [snadněji bitové kopie pro ladění](http://msdn.microsoft.com/Library/7d90ea7a-150f-4f97-98a7-f9c26541b9a3). Toto nastavení má následující možnosti:

- **None**

  Určuje, že nebudou vydány žádné informace o ladění.

- **Úplná**

  Umožňuje připojení ladicího programu spuštěného programu.

- **pdbonly**

  Umožňuje zdrojového kódu, ladění, když program běží v ladicím programu, ale zobrazí jenom assembleru po spuštěným programem k ladicího programu.
- **Přenositelností**

  Vytváří. Soubor PDB, soubor platformy konkrétní, přenosné symbol, který poskytuje jiných nástrojů, zejména ladicí programy, informace o tom, co je v hlavní spustitelný soubor a jak bylo vytvořeno. V tématu [přenosné PDB](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) Další informace.

- **Embedded**

  Vložení informací o přenosné symbolu do sestavení. Žádné externí. Soubor PDB vytváří.

Další informace najdete v tématu [/Debug (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/debug-compiler-option).

**Soubor zarovnání** Určuje velikost oddílů ve výstupním souboru. Platné hodnoty jsou **512**, **1024**, **2048**, **4096**, a **8192**. Tyto hodnoty se měří v bajtech. Každý oddíl bude zarovnán na hranici, která je násobkem tato hodnota, které mají vliv na velikost výstupního souboru. Další informace najdete v tématu [/filealign (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/filealign-compiler-option).

**Základní adresa knihovny** určuje upřednostňovaná základní adresa, na které se mají načíst knihovnu DLL. Výchozí základní adresy knihovny DLL se nastavuje pomocí [!INCLUDE[dnprdnshort](../../code-quality/includes/dnprdnshort_md.md)] modul common language runtime. Další informace najdete v tématu [/BaseAddress (možnosti kompilátoru C#)](/dotnet/csharp/language-reference/compiler-options/baseaddress-compiler-option).

## <a name="see-also"></a>Viz také

- [Možnosti kompilátoru jazyka C#](/dotnet/csharp/language-reference/compiler-options/index)
- [Stránka Sestavení, Návrhář projektu (C#)](../../ide/reference/build-page-project-designer-csharp.md)