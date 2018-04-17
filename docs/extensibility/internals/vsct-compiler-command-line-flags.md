---
title: Příznaky příkazového řádku kompilátoru VSCT | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, compiling
- command-table file compilation (VSCT files)
ms.assetid: 9dc6c33f-e6cf-4cf2-9b05-e8f7bfac1cfb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 6e2e1045adb451c7f4dd06b888fca356d26b7ff3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="vsct-compiler-command-line-flags"></a>Příznaky příkazového řádku kompilátoru VSCT
Kompilátor Visual Studio příkaz tabulky (VSCT) poskytuje přepínače příkazového řádku k zajištění úspěšné kompilace .vsct souborů.  
  
## <a name="command-line-parameters"></a>Parametry příkazového řádku  
 Chcete-li zobrazit základní nápovědu VSCT z [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **příkaz** okno, přejděte na *cesta instalace Visual Studio SDK*\VisualStudioIntegration\Tools\Bin\ složku a typ:  
  
```  
vsct /?  
```  
  
 Tento příkaz vrátí:  
  
```  
Microsoft (R) Visual Studio (R) Command Table Compiler Version 3.00.2000  
  
Syntax: vsct <infile> [<outfile>] [-S[symbols file]] [-D<preprocessor-define>]*  
[-I<include-path>]* [-L<language>] [-E[C|H|N]:<name>]  
  
  -D    Specify any additional preprocessor defines  
  -I    Indcate what additional include paths to send to the preprocessor  
  -L    Specify the langauge to use when selecting strings  
  -E    Emit C# objects in the specified namespace for command items,  
        folowed by [L|F|H|N]:<value>  
        F = Name of the file to emit (used if -EL is provided)  
        L = Name of a language providing a CodeDOM provider  
        N = namespace (required if -EL is provided)  
        H = C++ header  
  -c    Clean build skipping dependancy checks  
  -v    Verbose output  
```  
  
> [!NOTE]
>  Znaky - (pomlčka) a / (lomítko) jsou obě přijatý zápis pro označující parametry příkazového řádku.  
  
 Přijatelné příznaky a jejich významu jsou následujícím způsobem.  
  
|přepínače|Popis|  
|------------|-----------------|  
|-D|Zadejte jakékoli další definované symboly.|  
|-I|Označuje, že další zahrnout cesty, které se mají použít při rozpoznávání odkazů na soubor.|  
|-L|Zadejte <xref:System.Globalization.CultureInfo> název jazykové verze, například "en US".|  
|-E|Emitování objekty jazyka C# v určeném oboru názvů pro příkaz položky, za nímž následuje [C&#124;H&#124;N]:*filename*kde C = C#, H = C++ záhlaví, N = oboru názvů. Obor názvů je vyžadována pro C#.|  
|-v|Podrobný výstup.|  
  
 -L přepínač dá pokyn kompilátoru chcete vybrat skupinu řetězců za účelem vytvoření .cto binární soubor, který odpovídá danou <xref:System.Globalization.CultureInfo> název jazykové verze. Zadaná jazyková verze název by měl odpovídat atributu jazyk jednoho nebo více [řetězce Element](../../extensibility/strings-element.md) v souboru .vsct. Pokud element řetězce nemá žádné atributy jazyk, je zděděn z obsahující [CommandTable Element](../../extensibility/commandtable-element.md).  
  
 Soubor .vsct může mít více prvků řetězce a každý může mít jiný atribut Language. Globalizace je dosaženo tím opakované spouštění VSCT kompilátoru a změna přepínače -L pro každý název jazykové verze.  
  
 Pokud daný název jazykové verze přepínačem -L neodpovídá atribut Language libovolný element řetězce, kompilátor pokusí tak, aby odpovídaly jazyk a není oblast. Například pokud "en US" nelze najít, kompilátor pokusí "en" místo. Pokud neexistuje pokusí aktuální jazykovou verzi operačního systému. Pokud neexistuje zkompiluje první prvek řetězce, které najde.  
  
 -E přepínač lze použít pro vydávání soubor hlaviček stylu jazyka C, který obsahuje znaky, které jsou používány v tabulce příkaz nebo pro vydávání soubor C#, který obsahuje objekty pro příkaz symboly.  
  
 -D a - I mít přepínače syntaxe Cl.exe C preprocesoru příznaky, které mají stejný název. -D definice, které mají formát X = Y se používají pro rozšíření na základě XML \<definovaná > testů v `Condition` atributy. -I cesty zahrnutí slouží k přeložení \<zahrnout >, \<Extern > a \<rastrový obrázek > soubor odkazy. Další informace najdete v tématu [referenční dokumentace schématu XML VSCT](../../extensibility/vsct-xml-schema-reference.md).  
  
 Kompilátor VSCT můžete také dekompilaci dříve vytvořený binární soubor. Chcete-li to provést, zadat binárního souboru pro \<Vstupní_soubor >.   Pokud binární soubor byl vytvořen kompilátorem VSCT, bude mít jeho symboly již vložených a vytvoří výstupní symbolický název v \<symboly > část výstupu. Pokud binárního souboru bylo vytvořeno kompilátorem CTC, výstup bude obsahovat skutečné identifikátory a identifikátory GUID. Pokud *.ctsym soubor, který je produkovaný aktuálních verzích Ctc.exe ve stejné složce jako binárního souboru vstupního souboru se symboly načtený ze souboru se použije pro výstup.  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio příkaz tabulky (. Soubory Vsct)](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [Referenční dokumentace schématu VSCT XML](../../extensibility/vsct-xml-schema-reference.md)   
 [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)