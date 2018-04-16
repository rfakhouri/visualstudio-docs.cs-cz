---
title: MIDL – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCMidlTool.ServerStubFile
- VC.Project.VCMidlTool.ApplicationConfigurationMode
- VC.Project.VCMidlTool.GenerateServerFiles
- VC.Project.VCMidlTool.ClientStubFile
- VC.Project.VCMidlTool.LocaleID
- VC.Project.VCMidlTool.GenerateClientFiles
- VC.Project.VCMidlTool.SuppressCompilerWarnings
- VC.Project.VCMidlTool.TypeLibFormat
- vc.task.midl
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild (Visual C++), MIDL task
- MIDL task (MSBuild (Visual C++))
ms.assetid: 727efa8c-3336-40b8-8bef-ae6cbd77a422
caps.latest.revision: 8
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 51ed6c8c34fd5aa37eebffabcda077ca8554c498
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="midl-task"></a>MIDL – úloha
Zabalí nástroj Microsoft rozhraní Definition Language (MIDL) kompilátoru midl.exe. Další informace najdete v tématu "Reference k příkazovému řádku MIDL" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **MIDL** úloh. Většina úloh parametry a několik sad parametrů, odpovídají možnosti příkazového řádku.  
  
-   **AdditionalIncludeDirectories**  
  
     Volitelné **řetězec []** parametr.  
  
     Adresář přidá do seznamu adresáře, které budou prohledávány pro importované soubory IDL, zahrnuté hlavičkových souborů a konfigurační soubory aplikace (ACF).  
  
     Další informace najdete v tématu **/I** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **AdditionalOptions**  
  
     Volitelné **řetězec** parametr.  
  
     Seznam možností příkazového řádku. Například **"***nebo možnost 1 /option2 /option#*". Tento parametr použijte k určení možnosti příkazového řádku, které nejsou reprezentovány jakékoli jiné parametr MIDL úloh.  
  
     Další informace najdete v tématu "Reference k příkazovému řádku MIDL" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **ApplicationConfigurationMode**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, vám umožní používat některé ACF klíčová slova v souboru IDL.  
  
     Další informace najdete v tématu **/app_config** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **ClientStubFile**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název souboru se zakázaným inzerováním klienta pro rozhraní RPC.  
  
     Další informace najdete v tématu **/cstub** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu. Viz také **ServerStubFile** parametr v této tabulce.  
  
-   **CPreprocessOptions**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje možnosti, které mají být předána do C/C++ preprocessor. Zadejte seznam preprocesoru možností oddělených mezerami.  
  
     Další informace najdete v tématu **/cpp_opt** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **DefaultCharType**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje výchozí typ znak, který kompilátor jazyka C použije kompilace generovaného kódu.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    |Hodnota|Možnost příkazového řádku|  
    |-----------|--------------------------|  
    |**Podepsané**|**/ Char podepsané**|  
    |**Bez znaménka**|**/ Char bez znaménka**|  
    |**Ascii**|**/char ascii7**|  
  
     Další informace najdete v tématu **/char** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **DllDataFileName**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název souboru pro vygenerovaného *dlldata* soubor pro proxy server knihovny DLL.  
  
     Další informace najdete v tématu **/dlldata** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **EnableErrorChecks**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje typ kontroly, že generovaný zástupných procedur bude provádět v době běhu chyb.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    |Hodnota|Možnost příkazového řádku|  
    |-----------|--------------------------|  
    |**None**|**/ Error none**|  
    |**EnableCustom**|**/ Error**|  
    |**Všechny**|**všechny/Error**|  
  
     Další informace najdete v tématu **/Error** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **ErrorCheckAllocations**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, zkontrolovat chyby při nedostatku paměti.  
  
     Další informace najdete v tématu **/Error přidělení** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **ErrorCheckBounds**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`kontroluje velikost různých vyhovující a různých polí proti specifikace délky přenosu.  
  
     Další informace najdete v tématu **/Error bounds_check** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **ErrorCheckEnumRange**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, zkontroluje, zda jsou hodnoty výčtu ve povolený rozsah.  
  
     Další informace najdete v tématu **/Error výčtu** možnost v Nápověda příkazového řádku (**/?**) pro midl.exe.  
  
-   **ErrorCheckRefPointers**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, zkontrolujte, zda zástupných procedur klienta se budou předávat žádné ukazatele odkazu s hodnotou null.  
  
     Další informace najdete v tématu **/Error ref** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **ErrorCheckStubData**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, vygeneruje se zakázaným inzerováním, který zachytí unmarshaling výjimky na straně serveru a rozšiřuje je zpět do klienta.  
  
     Další informace najdete v tématu **/Error stub_data** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **GenerateClientFiles**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje, jestli kompilátor generuje klienta C zdrojové soubory pro rozhraní RPC.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    |Hodnota|Možnost příkazového řádku|  
    |-----------|--------------------------|  
    |**None**|**/Client none**|  
    |**Se zakázaným inzerováním**|**/Client se zakázaným inzerováním**|  
  
     Další informace najdete v tématu **/client** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **GenerateServerFiles**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje, jestli kompilátor generuje serverový C zdrojové soubory pro rozhraní RPC.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    |Hodnota|Možnost příkazového řádku|  
    |-----------|--------------------------|  
    |**None**|**/ Server none**|  
    |**Se zakázaným inzerováním**|**/ Server se zakázaným inzerováním**|  
  
     Další informace najdete v tématu **/server** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **GenerateStublessProxies**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, generuje plně interpretovaný zástupných procedur společně s provizorní proxy pro rozhraní objektu.  
  
     Další informace najdete v tématu **/oicf** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **GenerateTypeLibrary**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, soubor knihovny (.tlb) typu nevygenerovala.  
  
     Další informace najdete v tématu **/notlb** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **HeaderFileName**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název souboru generovaného záhlaví.  
  
     Další informace najdete v tématu **/h** nebo **/header** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **IgnoreStandardIncludePath**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, úlohu MIDL v adresářích jenom zadat pomocí **AdditionalIncludeDirectories** přepínače a ignoruje aktuálního adresáře a adresáře, určené proměnnou prostředí zahrnout.  
  
     Další informace najdete v tématu **/no_def_idir** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **InterfaceIdentifierFileName**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název *rozhraní identifikátor souboru* pro rozhraní modelu COM. Přepíše výchozí název získat přidáním "_i.c" k názvu souboru IDL.  
  
     Další informace najdete v tématu **/iid** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **LocaleID**  
  
     Volitelné **int** parametr.  
  
     Určuje, *identifikátor národního prostředí* umožňující použití mezinárodní znaky v vstupní soubory, názvy souborů a cesty k adresáři. Zadejte identifikátor národního prostředí decimal.  
  
     Další informace najdete v tématu **LCID** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu. Viz také "Národní prostředí ID přiřazené službou Microsoft" na webu MSDN.  
  
-   **MkTypLibCompatible**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, vyžaduje formát vstupního souboru, aby byl kompatibilní s verzí mktyplib.exe 2.03.  
  
     Další informace najdete v tématu **/mktyplib203** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu. Viz také "Syntaxe souboru ODL" na webu MSDN.  
  
-   **OutputDirectory**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje výchozí adresář, kde MIDL – úloha zapíše výstupní soubory.  
  
     Další informace najdete v tématu **/out** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **PreprocessorDefinitions**  
  
     Volitelné **řetězec []** parametr.  
  
     Určuje jeden nebo více *definuje*; to znamená, název a volitelná hodnota má být předán preprocesor C jako v případě podle `#define` – direktiva. Každý definovat hodnotu, *název [= value]*.  
  
     Další informace najdete v tématu **/D** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu. Další informace naleznete **UndefinePreprocessorDefinitions** parametr v této tabulce.  
  
-   **ProxyFileName**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název souboru pro proxy rozhraní pro rozhraní modelu COM.  
  
     Další informace najdete v tématu **/proxy** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **RedirectOutputAndErrors**  
  
     Volitelné **řetězec** parametr.  
  
     Provede přesměrování výstupu, jako je například chybové zprávy a upozornění z standardní výstup do určeného souboru.  
  
     Další informace najdete v tématu **/o** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **ServerStubFile**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název souboru se zakázaným inzerováním server pro rozhraní RPC.  
  
     Další informace najdete v tématu **/sstub** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu. Další informace naleznete **ClientStubFile** parametr v této tabulce.  
  
-   **Zdroj**  
  
     Požadované `ITaskItem[]` parametr.  
  
     Určuje seznam zdrojové soubory, které jsou oddělené mezerami.  
  
-   **StructMemberAlignment**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje zarovnání (*balení úroveň*) struktur v cílovém systému.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    |Hodnota|Možnost příkazového řádku|  
    |-----------|--------------------------|  
    |**NotSet**|*\<žádné >*|  
    |**1**|**/Zp1**|  
    |**2**|**/Zp2**|  
    |**4**|**/Zp4**|  
    |**8**|**/Zp8**|  
  
     Další informace najdete v tématu **/Zp** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu. **/Zp** je ekvivalentní **, pack** možnost a starší **/ align** možnost.  
  
-   **SuppressCompilerWarnings**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, potlačí zprávy upozornění z MIDL úlohy.  
  
     Další informace najdete v tématu **/no_warn** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **SuppressStartupBanner**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, zabraňuje zobrazení číslo zprávy o autorských právech a verzi, po spuštění úlohy.  
  
     Další informace najdete v tématu **/nologo** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **TargetEnvironment**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje prostředí, ve kterém je aplikace spuštěná.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    |Hodnota|Možnost příkazového řádku|  
    |-----------|--------------------------|  
    |**NotSet**|*\<žádné >*|  
    |**Win32**|**win32/env**|  
    |**Itanium**|**/ env ia64**|  
    |**X64**|**/env x64**|  
  
     Další informace najdete v tématu **/env** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **TrackerLogDirectory**  
  
     Volitelné `String` parametr.  
  
     Určuje zprostředkující adresář, kde jsou uloženy protokoly sledování pro tuto úlohu.  
  
-   **TypeLibFormat**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje formát souboru typu knihovna.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    |Hodnota|Možnost příkazového řádku|  
    |-----------|--------------------------|  
    |**NewFormat**|**/newtlb**|  
    |**OldFormat**|**/oldtlb**|  
  
     Další informace najdete v tématu **/newtlb** a **/oldtlb** možnosti v "Příkazového řádku MIDL" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **TypeLibraryName**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název souboru knihovny typu.  
  
     Další informace najdete v tématu **/TLB** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **UndefinePreprocessorDefinitions**  
  
     Volitelné **řetězec []** parametr.  
  
     Odebere všechny předchozí definice názvu předáním názvu pro preprocesor C jako v případě podle `#undefine` – direktiva. Zadejte jeden nebo více dříve definované názvy.  
  
     Další informace najdete v tématu **/U** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu. Další informace naleznete **PreprocessorDefinitions** parametr v této tabulce.  
  
-   **ValidateAllParameters**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, vygeneruje další chyb informace, které se používá k provádění kontrol integrity za běhu. Pokud `false`, nevygenerovala informace chyb.  
  
     Další informace najdete v tématu **/ robust** a **/no_robust** možnosti v "Příkazového řádku MIDL" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **WarnAsError**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, zpracovává všech upozornění jako chyby.  
  
     Pokud **WarningLevel** není zadán parametr úloh MIDL, upozornění na výchozí úrovni, úroveň 1, jsou považovány za chyby.  
  
     Další informace najdete v tématu **wdn** možnosti v "Příkazového řádku MIDL" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu. Další informace naleznete **WarningLevel** parametr v této tabulce.  
  
-   **WarningLevel**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje závažnost (*úroveň pro upozornění*) upozornění pro vydávání. Bez upozornění jsou vydávány na hodnotu 0. Jinak je vygenerované upozornění, pokud jeho úroveň pro upozornění je číselné hodnoty menší než nebo rovna zadané hodnotě.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    |Hodnota|Možnost příkazového řádku|  
    |-----------|--------------------------|  
    |**0**|**/W0**|  
    |**1**|**/W1**|  
    |**2**|**/W2**|  
    |**3**|**/W3**|  
    |**4**|**/W4**|  
  
     Další informace najdete v tématu **/W** možnost v "Příkazového řádku MIDL" [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu. Další informace naleznete **WarnAsError** parametr v této tabulce.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)