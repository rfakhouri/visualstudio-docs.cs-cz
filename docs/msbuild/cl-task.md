---
title: CL – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing
- vc.task.cl
- VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild (Visual C++), CL task
- CL task (MSBuild (Visual C++))
ms.assetid: 651ba971-b755-4f03-a549-4816beb3cc0d
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f587eded84863a36fb2c293680cebd7668864c76
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="cl-task"></a>CL – úloha
Zabalí nástroj kompilátoru Visual C++ cl.exe. Kompilátor vytvoří spustitelné soubory (.exe), dynamická knihovna (DLL) soubory nebo soubory kódu modulu (.netmodule). Další informace najdete v tématu [– možnosti kompilátoru](/cpp/build/reference/compiler-options).  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **CL** úloh. Většina úloh parametry a několik sad parametrů, odpovídají možnosti příkazového řádku.  
  
-   **AdditionalIncludeDirectories**  
  
     Volitelný parametr řetězec [].  
  
     Přidá do seznamu adresáře, které se vyhledávají zahrnout soubory adresář.  
  
     Další informace najdete v tématu [/I (Další adresáře Include)](/cpp/build/reference/i-additional-include-directories).  
  
-   **AdditionalOptions**  
  
     Volitelný parametr řetězce.  
  
     Seznam možností příkazového řádku. Například "/*možnost 1* /*option2* /*možnost #*". Tento parametr použijte k určení možnosti příkazového řádku, které nejsou reprezentovány druhý parametr úloh.  
  
     Další informace najdete v tématu [– možnosti kompilátoru](/cpp/build/reference/compiler-options).  
  
-   **AdditionalUsingDirectories**parametr volitelný řetězec [].  
  
     Určuje adresář, který bude kompilátor hledat řešení předaný odkazů na soubor **#using** – direktiva.  
  
     Další informace najdete v tématu [/AI (zadat adresáře metadat)](/cpp/build/reference/ai-specify-metadata-directories).  
  
-   **AlwaysAppend**  
  
     Volitelný parametr řetězce.  
  
     Řetězec získá to vždy vygenerované na příkazovém řádku. Výchozí hodnota je "**/c**".  
  
-   **AssemblerListingLocation**  
  
     Vytvoří seznam soubor, který obsahuje sestavení kódu.  
  
     Další informace najdete v tématu **/Fa** možnost [/FA, /Fa (soubor výpis)](/cpp/build/reference/fa-fa-listing-file).  
  
-   **AssemblerOutput**  
  
     Volitelný parametr řetězce.  
  
     Vytvoří seznam soubor, který obsahuje sestavení kódu.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **NoListing** - *\<žádné >*  
  
    -   **AssemblyCode** - **/FA**  
  
    -   **AssemblyAndMachineCode** - **/FAc**  
  
    -   **AssemblyAndSourceCode** - **/FAs**  
  
    -   **Všechny** - **/FAcs**  
  
     Další informace najdete v tématu **/FA**, **/FAc**, **/FAs**, a **/FAcs** možnosti v [/FA, /Fa (výpis soubor)](/cpp/build/reference/fa-fa-listing-file).  
  
-   **BasicRuntimeChecks**  
  
     Volitelný parametr řetězce.  
  
     Povolí nebo zakáže funkci kontroly Chyba spuštění ve spojení s [runtime_checks –](/cpp/preprocessor/runtime-checks) – Direktiva pragma.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **Výchozí** -                          *\<žádné >*  
  
    -   **StackFrameRuntimeCheck** - **/RTCs**  
  
    -   **UninitializedLocalUsageCheck** - **/RTCu**  
  
    -   **EnableFastChecks** -                          **/RTC1**  
  
     Další informace najdete v tématu [/RTC (kontroluje chyby Run-Time)](/cpp/build/reference/rtc-run-time-error-checks).  
  
-   **BrowseInformation**  
  
     Volitelný parametr, logická hodnota.  
  
     Pokud `true`, vytvoří soubor informací o procházení.  
  
     Další informace najdete v tématu **/FR** možnost [/FR, /Fr (vytvořit. Soubor SBR)](/cpp/build/reference/fr-fr-create-dot-sbr-file).  
  
-   **BrowseInformationFile**  
  
     Volitelný parametr řetězce.  
  
     Určuje název souboru pro soubor s informacemi o procházení.  
  
     Další informace najdete v tématu **BrowseInformation** parametr v této tabulce a také najdete [/FR, /Fr (vytvořit. Soubor SBR)](/cpp/build/reference/fr-fr-create-dot-sbr-file).  
  
-   **BufferSecurityCheck**  
  
     Volitelný parametr, logická hodnota.  
  
     Pokud `true`, zjistí některé přetečení vyrovnávací paměti, které přepsat zpáteční adresu běžné technika zneužitím kód, který nevynucuje omezení velikosti vyrovnávací paměti.  
  
     Další informace najdete v tématu [/GS (Kontrola zabezpečení vyrovnávací paměti)](/cpp/build/reference/gs-buffer-security-check).  
  
-   **BuildingInIDE**  
  
     Volitelný parametr, logická hodnota.  
  
     Pokud `true`, znamená, že **MSBuild** je vyvolané rozhraní IDE. V opačném **MSBuild** je vyvolat na příkazovém řádku.  
  
-   **CallingConvention**  
  
     Volitelný parametr řetězce.  
  
     Určuje konvence volání, která pořadí, ve které funkci argumenty jsou vloženy do zásobníku, určuje, zda volající funkce nebo volaná funkce odebere argumenty v zásobníku volání na konci, a název architekturu konvence, kompilátor používá k identifikaci jednotlivých funkcí.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **Cdecl** - **/Gd**  
  
    -   **FastCall** -                          **GR**  
  
    -   **StdCall** -                          **/Gz**  
  
     Další informace najdete v tématu [/Gd, / GR, / gv, /Gz (konvence volání)](/cpp/build/reference/gd-gr-gv-gz-calling-convention).  
  
-   **CompileAs**  
  
     Volitelný parametr řetězce.  
  
     Určuje, jestli se pro kompilaci vstupní soubor jako zdrojový soubor jazyka C nebo C++.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **Výchozí** - *\<žádné >*  
  
    -   **CompileAsC** - **/TC**  
  
    -   **CompileAsCpp** - **/TP**  
  
     Další informace najdete v tématu [/Tc, /Tp, /TC, /TP (zadejte zdrojový soubor typu)](/cpp/build/reference/tc-tp-tc-tp-specify-source-file-type).  
  
-   **CompileAsManaged**  
  
     Volitelný parametr řetězce.  
  
     Umožňuje aplikací a součástí, které chcete používat funkce z common language runtime (CLR).  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **false** - *\<žádné >*  
  
    -   **Hodnota TRUE,** -   **/CLR**  
  
    -   **Čistý** -   **/CLR: pure**  
  
    -   **Bezpečné** -   **/CLR: safe**  
  
    -   **OldSyntax** - **/clr:oldSyntax**  
  
     Další informace najdete v tématu [/CLR (kompilace Common Language Runtime)](/cpp/build/reference/clr-common-language-runtime-compilation).  
  
-   **CreateHotpatchableImage**  
  
     Volitelný parametr, logická hodnota.  
  
     Pokud `true`, říká kompilátoru připravit bitovou kopii pro *této technologie*. Tento parametr zajišťuje, že první pokyn každé funkce dva bajty, což je vyžadováno pro této technologie.  
  
     Další informace najdete v tématu [/hotpatch (vytvořit kopii opravitelnou za provozu)](/cpp/build/reference/hotpatch-create-hotpatchable-image).  
  
-   **DebugInformationFormat**  
  
     Volitelný parametr řetězce.  
  
     Vybere typ ladění informace, které jsou vytvořené pro vaši aplikaci a zda tyto informace jsou uchovávány v souborech objektu (.obj) nebo v databázi programu (PDB).  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **Minuskové** - **/Z7**  
  
    -   **ProgramDatabase** - **/Zi**  
  
    -   **EditAndContinue** - **/ZI**  
  
     Další informace najdete v tématu [/Z7, / zi, /ZI (formát informace ladění)](/cpp/build/reference/z7-zi-zi-debug-information-format).  
  
-   **DisableLanguageExtensions**  
  
     Volitelný parametr, logická hodnota.  
  
     Pokud **true**, říká kompilátoru pro vydávání chybu pro konstruktory jazyka, které nejsou kompatibilní se specifikací ANSI C nebo ANSI C++.  
  
     Další informace najdete v tématu **/Za** možnost [/Za, /Ze (zakázat jazyková rozšíření)](/cpp/build/reference/za-ze-disable-language-extensions).  
  
-   **DisableSpecificWarnings**  
  
     Volitelný parametr řetězec [].  
  
     Zakáže upozornění čísla, která jsou určené v seznamu oddělených středníky.  
  
     Další informace najdete v tématu `/wd` možnost [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, nebo jsme /wo, /Wv, wdn (úroveň upozornění)](/cpp/build/reference/compiler-option-warning-level).  
  
-   **EnableEnhancedInstructionSet**  
  
     Volitelný parametr řetězce.  
  
     Určuje architekturu pro generování kódu, který používá Streaming SIMD Extensions (SSE) a Streaming SIMD Extensions 2 (SSE2) pokyny.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **StreamingSIMDExtensions** - **/arch:SSE**  
  
    -   **StreamingSIMDExtensions2** - **/arch:SSE2**  
  
     Další informace najdete v tématu [/arch (x86)](/cpp/build/reference/arch-x86).  
  
-   **EnableFiberSafeOptimizations**  
  
     Volitelný parametr, logická hodnota.  
  
     Pokud `true`, podporují fiber zabezpečení pro data přidělené pomocí statické úložiště thread-local, tedy dat přidělené pomocí `__declspec(thread)`.  
  
     Další informace najdete v tématu [/gt (Podpora úložiště Thread-Local zabezpečenými Vlákénky) optického](/cpp/build/reference/gt-support-fiber-safe-thread-local-storage).  
  
-   **EnablePREfast**  
  
     Volitelný parametr, logická hodnota.  
  
     Pokud `true`, povolit analýza kódu.  
  
     Další informace najdete v tématu [/ analyze (Analýza kódu)](/cpp/build/reference/analyze-code-analysis).  
  
-   **ErrorReporting**  
  
     Volitelný parametr řetězce.  
  
     Umožňuje zadat informace o chybě (LED) interní kompilátoru přímo společnosti Microsoft. Ve výchozím nastavení v IDE sestavení je **výzva** a nastavení v sestavení příkazového řádku je **fronty**.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **Žádný** -   **/errorreport: žádné**  
  
    -   **Řádku** - **/errorReport:prompt**  
  
    -   **Fronty** - **/errorReport:queue**  
  
    -   **Odeslat** - **/errorReport:send**  
  
     Další informace najdete v tématu [/errorreport (sestava interními chybami kompilátoru)](/cpp/build/reference/errorreport-report-internal-compiler-errors).  
  
-   **ExceptionHandling**  
  
     Volitelný parametr řetězce.  
  
     Určuje model zpracování má být používána kompilátor výjimek.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **false** - *\<žádné >*  
  
    -   **Asynchronní** -   **/EHa**  
  
    -   **Sync** - **/EHsc**  
  
    -   **SyncCThrow** - **/EHs**  
  
     Další informace najdete v tématu [/EH (Model zpracování výjimek)](/cpp/build/reference/eh-exception-handling-model).  
  
-   **ExpandAttributedSource**  
  
     Volitelný parametr, logická hodnota.  
  
     Pokud `true`, vytvoří soubor seznamu, který se rozšířila atributy vloženy do zdrojového souboru.  
  
     Další informace najdete v tématu [/Fx (sloučení vloženého kódu)](/cpp/build/reference/fx-merge-injected-code).  
  
-   **FavorSizeOrSpeed**  
  
     Volitelný parametr řetězce.  
  
     Určuje, jestli upřednostnit rychlost kód velikost nebo kódu.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **Ani** - *\<žádné >*  
  
    -   **Velikost** - **/Os**  
  
    -   **Rychlost** - **/Ot**  
  
     Další informace najdete v tématu [/Os, /Ot (upřednostnit malý kód, upřednostnit rychlého kód)](/cpp/build/reference/os-ot-favor-small-code-favor-fast-code).  
  
-   **FloatingPointExceptions**  
  
     Volitelný parametr, logická hodnota.  
  
     Pokud `true`, umožňuje modelu spolehlivé výjimek plovoucí desetinné čárky. Výjimky, bude vyvolána ihned po se aktivují.  
  
     Další informace najdete v tématu nebo**fp: kromě** možnost [/fp (zadejte Floating-Point chování)](/cpp/build/reference/fp-specify-floating-point-behavior).  
  
-   **FloatingPointModel**  
  
     Volitelný parametr řetězce.  
  
     Nastaví procedura bod modelu.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **Přesné** - **/fp: přesné**  
  
    -   **Striktní** - **/fp: striktní**  
  
    -   **Rychlé** - **/fp:fast**  
  
     Další informace najdete v tématu [/fp (zadejte Floating-Point chování)](/cpp/build/reference/fp-specify-floating-point-behavior).  
  
-   **ForceConformanceInForLoopScope**  
  
     Volitelný parametr, logická hodnota.  
  
     Pokud `true`, implementuje standardní C++ chování v [pro](/cpp/cpp/for-statement-cpp) cykly, které používají rozšíření Microsoft ([/Ze](/cpp/build/reference/za-ze-disable-language-extensions)).  
  
     Další informace najdete v tématu [/Zc:forScope (vynutit dodržování pro obor cyklu for)](/cpp/build/reference/zc-forscope-force-conformance-in-for-loop-scope).  
  
-   **ForcedIncludeFiles**  
  
     Volitelné `String[]` parametr.  
  
     Způsobí, že preprocesor zpracovat jeden nebo více souborů Zadaná hlavička.  
  
     Další informace najdete v tématu [/FI (vynutit soubor začlenění název)](/cpp/build/reference/fi-name-forced-include-file).  
  
-   **ForcedUsingFiles**  
  
     Volitelné **řetězec []** parametr.  
  
     Způsobí, že preprocesoru zpracovat jeden nebo více zadaných **#using** soubory.  
  
     Další informace najdete v tématu [/FU (vynuceným názvem #using souboru)](/cpp/build/reference/fu-name-forced-hash-using-file).  
  
-   **FunctionLevelLinking**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, umožňuje kompilátoru na jednotlivé funkce balíček ve formě zabalené funkce (COMDATs).  
  
     Další informace najdete v tématu [/Gy (povolení propojení na úrovni funkcí)](/cpp/build/reference/gy-enable-function-level-linking).  
  
-   **GenerateXMLDocumentationFiles**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, příčiny kompilátoru zpracovat dokumentace komentáře ve zdrojových souborů kódu a vytvořit projektový soubor pro každý zdroj kódu soubor, který má dokumentační komentáře.  
  
     Další informace najdete v tématu [/DOC (zpracování dokumentačních komentářů) (C/C++)](/cpp/build/reference/doc-process-documentation-comments-c-cpp). Viz také **XMLDocumentationFileName** parametr v této tabulce.  
  
-   **IgnoreStandardIncludePath**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, zabrání kompilátoru hledání zahrnout soubory v adresářích zadaný v proměnné prostředí PATH a zahrnout.  
  
     Další informace najdete v tématu [/X (Ignorovat standardní cesty zahrnutí)](/cpp/build/reference/x-ignore-standard-include-paths).  
  
-   **InlineFunctionExpansion**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje úroveň vložené funkce rozšíření pro sestavení.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **Výchozí** - *\<žádné >*  
  
    -   **Zakázané** - **/Ob0**  
  
    -   **OnlyExplicitInline** - **/Ob1**  
  
    -   **AnySuitable** - **/Ob2**  
  
     Další informace najdete v tématu [/Ob (rozbalení vložené funkce)](/cpp/build/reference/ob-inline-function-expansion).  
  
-   **Intrinsicfunctions –**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, nahradí některé funkce volá s vnitřní nebo jinak speciální formy funkce, které pomáhají aplikace pracovat rychleji.  
  
     Další informace najdete v tématu [/Oi (Generovat vnitřní funkce)](/cpp/build/reference/oi-generate-intrinsic-functions).  
  
-   **MinimalRebuild**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, umožňuje musí zopakovat minimální opětovné sestavení, která určuje, zda C++ zdrojové soubory, které zahrnují změněné C++ třídy definice (uložené v souborech hlavičky ()).  
  
     Další informace najdete v tématu [/Gm (povolit minimální sestavení)](/cpp/build/reference/gm-enable-minimal-rebuild).  
  
-   **MultiProcessorCompilation**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, použít více procesorů pro kompilaci. Tento parametr vytvoří proces pro každý efektivní procesor v počítači.  
  
     Další informace najdete v tématu [/MP (sestavení pomocí několika procesů)](/cpp/build/reference/mp-build-with-multiple-processes). Další informace naleznete **ProcessorNumber** parametr v této tabulce.  
  
-   **ObjectFileName**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název objektu (.obj) soubor nebo adresář, který se má použít místo výchozí.  
  
     Další informace najdete v tématu [/Fo (název souboru objektů)](/cpp/build/reference/fo-object-file-name).  
  
-   **ObjectFiles**  
  
     Volitelné **řetězec []** parametr.  
  
     Seznam souborů objektu.  
  
-   **OmitDefaultLibName**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, vynechá výchozí název běhové knihovny jazyka C ze souboru objektu (.obj). Ve výchozím nastavení kompilátoru zařadí do souboru .obj směrovat linkeru do správné knihovny název knihovny.  
  
     Další informace najdete v tématu [/Zl (vypuštění název výchozí knihovny)](/cpp/build/reference/zl-omit-default-library-name).  
  
-   **OmitFramePointers**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, potlačí vytvoření ukazatele na rámce v zásobníku volání.  
  
     Další informace najdete v tématu [/Oy (vynechání ukazatele)](/cpp/build/reference/oy-frame-pointer-omission).  
  
-   **OpenMPSupport**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, způsobí, že kompilátor zpracovat OpenMP – klauzule a direktivy.  
  
     Další informace najdete v tématu [/OpenMP (povolit podporu OpenMP 2.0)](/cpp/build/reference/openmp-enable-openmp-2-0-support).  
  
-   **Optimalizace**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje různé optimalizace kódu pro rychlost a velikost.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **Zakázané** - **/Od**  
  
    -   **MinSpace** - **/O1**  
  
    -   **MaxSpeed** -   **/O2**  
  
    -   **Úplné** - **/Ox**  
  
     Další informace najdete v tématu [/O možnosti (Optimalizace kódu)](/cpp/build/reference/o-options-optimize-code).  
  
-   **PrecompiledHeader**  
  
     Volitelné **řetězec** parametr.  
  
     Vytvořit nebo použít soubor předkompilovaných hlaviček (.pch) během sestavení.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **NotUsing** - *\<žádné >*  
  
    -   **Vytvoření** - **/Yc**  
  
    -   **Použití** - **/Yu**  
  
     Další informace najdete v tématu [/Yc (Vytvořit předkompilovaný hlavičkový soubor)](/cpp/build/reference/yc-create-precompiled-header-file) a [/Yu (Použít předkompilovaný hlavičkový soubor)](/cpp/build/reference/yu-use-precompiled-header-file). Další informace naleznete **PrecompiledHeaderFile** a **PrecompiledHeaderOutputFile** parametry v této tabulce.  
  
-   **PrecompiledHeaderFile**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název souboru předkompilovaných hlaviček chcete vytvořit nebo použít.  
  
     Další informace najdete v tématu [/Yc (Vytvořit předkompilovaný hlavičkový soubor)](/cpp/build/reference/yc-create-precompiled-header-file) a [/Yu (Použít předkompilovaný hlavičkový soubor)](/cpp/build/reference/yu-use-precompiled-header-file).  
  
-   **PrecompiledHeaderOutputFile**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název cesty pro předkompilované hlavičky místo použití výchozí název cesty.  
  
     Další informace najdete v tématu [/Fp (název. Soubor pch)](/cpp/build/reference/fp-name-dot-pch-file).  
  
-   **PreprocessKeepComments**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, zachová komentáře při předběžném zpracování.  
  
     Další informace najdete v tématu [/C (zachovat komentáře při předběžném zpracování)](/cpp/build/reference/c-preserve-comments-during-preprocessing).  
  
-   **PreprocessorDefinitions**  
  
     Volitelné `String[]` parametr.  
  
     Definuje předběžného zpracování symbol pro zdrojový soubor.  
  
     Další informace najdete v tématu [/D (Definice preprocesoru)](/cpp/build/reference/d-preprocessor-definitions).  
  
-   **PreprocessOutput**  
  
     Volitelné `ITaskItem[]` parametr.  
  
     Definuje pole výstup preprocesoru položek, které je možné využívat a vygenerované úlohami.  
  
-   **PreprocessOutputPath**  
  
     Volitelné `String` parametr.  
  
     Určuje název výstupního souboru, ke kterému **PreprocessToFile** zapíše předběžně zpracované výstupní parametr.  
  
     Další informace najdete v tématu [/Fi (předběžné zpracování názvu výstupního souboru)](/cpp/build/reference/fi-preprocess-output-file-name).  
  
-   **PreprocessSuppressLineNumbers**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, upraví C a C++ zdrojové soubory a zkopíruje předběžně zpracované soubory do standardního výstupního zařízení.  
  
     Další informace najdete v tématu [/EP (předběžné zpracování do direktiv bez #line direktivy)](/cpp/build/reference/ep-preprocess-to-stdout-without-hash-line-directives).  
  
-   **PreprocessToFile**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, upraví C a C++ zdrojových souborů a předběžně zpracované výstup zapisuje do souboru.  
  
     Další informace najdete v tématu [/P (předběžné zpracování souboru)](/cpp/build/reference/p-preprocess-to-a-file).  
  
-   **ProcessorNumber**  
  
     Volitelné `Integer` parametr.  
  
     Určuje maximální počet procesorů pro použití v kompilaci s více procesory. Tento parametr použijte v kombinaci s **MultiProcessorCompilation** parametr.  
  
-   **ProgramDataBaseFileName**  
  
     Volitelné `String` parametr.  
  
     Určuje název souboru pro soubor databáze (PDB) programu.  
  
     Další informace najdete v tématu [/Fd (název souboru databáze programu)](/cpp/build/reference/fd-program-database-file-name).  
  
-   **RuntimeLibrary**  
  
     Volitelné `String` parametr.  
  
     Určuje, jestli se knihovny DLL s více vlákny modul a vybere instalačních nebo ladicích verzích běhové knihovny.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **Vícevláknové** -   **/MT**  
  
    -   **MultiThreadedDebug** - **/MTd**  
  
    -   **MultiThreadedDLL** - **/MD**  
  
    -   **MultiThreadedDebugDLL** - **/MDd**  
  
     Další informace najdete v tématu [/MD, / MT, /LD (použít běhovou knihovnu)](/cpp/build/reference/md-mt-ld-use-run-time-library).  
  
-   **RuntimeTypeInfo**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, přidá kód ke kontrole typy objektů C++ v době běhu (informace běhového typu).  
  
     Další informace najdete v tématu [/GR (Povolit Run-Time informace typu)](/cpp/build/reference/gr-enable-run-time-type-information).  
  
-   **ShowIncludes**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, způsobí, že kompilátor výstup seznam zahrnout soubory.  
  
     Další informace najdete v tématu [/showincludes vložených (seznam souborů)](/cpp/build/reference/showincludes-list-include-files).  
  
-   **SmallerTypeCheck**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, pokud hodnota je přiřazena k menší datový typ a vede ke ztrátě dat nahlásí chybu běhu.  
  
     Další informace najdete v tématu **/RTCc** možnost [/RTC (kontroluje chyby Run-Time)](/cpp/build/reference/rtc-run-time-error-checks).  
  
-   **Zdroje**  
  
     Požadované `ITaskItem[]` parametr.  
  
     Určuje seznam zdrojové soubory, které jsou oddělené mezerami.  
  
-   **StringPooling**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, umožňuje kompilátor vytvoří jednu kopii identické řetězce do bitové kopie programu.  
  
     Další informace najdete v tématu [/GF (odstranění duplicitních řetězců)](/cpp/build/reference/gf-eliminate-duplicate-strings).  
  
-   **StructMemberAlignment**  
  
     Volitelné `String` parametr.  
  
     Určuje zarovnání bajtů pro všechny členy do struktury.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **Výchozí** - **/Zp1**  
  
    -   **1Byte** - **/Zp1**  
  
    -   **2Bytes** - **/Zp2**  
  
    -   **4Bytes** - **/Zp4**  
  
    -   **8Bytes** - **/Zp8**  
  
    -   **16Bytes** - **/Zp16**  
  
     Další informace najdete v tématu [/Zp (zarovnání členů struktury)](/cpp/build/reference/zp-struct-member-alignment).  
  
-   **SuppressStartupBanner**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, zabraňuje zobrazení číslo zprávy o autorských právech a verzi, po spuštění úlohy.  
  
     Další informace najdete v tématu [/nologo (Potlačit úvodní nápis při spouštění) (C/C++)](/cpp/build/reference/nologo-suppress-startup-banner-c-cpp).  
  
-   **TrackerLogDirectory**  
  
     Volitelné `String` parametr.  
  
     Určuje zprostředkující adresář, kde jsou uloženy protokoly sledování pro tuto úlohu.  
  
     Další informace najdete v tématu **TLogReadFiles** a **TLogWriteFiles** parametry v této tabulce.  
  
-   **TreatSpecificWarningsAsErrors**  
  
     Volitelné **řetězec []** parametr.  
  
     Zadaný seznam upozornění kompilátoru považuje za chyby.  
  
     Další informace najdete v tématu **/we** `n` možnost [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, nebo jsme /wo, /Wv, wdn (úroveň upozornění)](/cpp/build/reference/compiler-option-warning-level).  
  
-   **TreatWarningAsError**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, považovat všechny kompilátoru upozornění jako chyby.  
  
     Další informace najdete v tématu **wdn** možnost [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, nebo jsme /wo, /Wv, wdn (úroveň upozornění)](/cpp/build/reference/compiler-option-warning-level).  
  
-   **TreatWChar_tAsBuiltInType**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, považovat `wchar_t` typ jako nativního typu.  
  
     Další informace najdete v tématu [/Zc: wchar_t (wchar_t je nativní typ)](/cpp/build/reference/zc-wchar-t-wchar-t-is-native-type).  
  
-   **UndefineAllPreprocessorDefinitions**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, undefines symboly specifické pro společnost Microsoft, které definuje kompilátoru.  
  
     Další informace najdete v tématu **/u** možnost [/U, /u (nedefinované symboly)](/cpp/build/reference/u-u-undefine-symbols).  
  
-   **UndefinePreprocessorDefinitions**  
  
     Volitelné `String[]` parametr.  
  
     Určuje seznam jedné nebo více preprocesoru symbolů pro nedefinované.  
  
     Další informace najdete v tématu **/U** možnost [/U, /u (nedefinované symboly)](/cpp/build/reference/u-u-undefine-symbols).  
  
-   **UseFullPaths**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, zobrazí úplnou cestu soubory zdrojového kódu předaný kompilátoru v diagnostice.  
  
     Další informace najdete v tématu [/FC (úplná cesta z souboru zdrojového kódu v diagnostice)](/cpp/build/reference/fc-full-path-of-source-code-file-in-diagnostics).  
  
-   **UseUnicodeForAssemblerListing**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, způsobí, že výstupní soubor má být vytvořen ve formátu UTF-8.  
  
     Další informace najdete v tématu **/FAu** možnost [/FA, /Fa (soubor výpis)](/cpp/build/reference/fa-fa-listing-file).  
  
-   **WarningLevel**  
  
     Volitelné `String` parametr.  
  
     Určuje nejvyšší úroveň upozornění, která má být vytvořen pomocí kompilátoru.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **TurnOffAllWarnings** - **/W0**  
  
    -   **Level1** - **/W1**  
  
    -   **Level2** - **/W2**  
  
    -   **Level3** - **/W3**  
  
    -   **Level4** - **/W4**  
  
    -   **EnableAllWarnings** -   **/horní**  
  
     Další informace najdete v tématu **/W***n* možnost [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, nebo jsme /wo, /Wv, wdn (úroveň upozornění)](/cpp/build/reference/compiler-option-warning-level).  
  
-   **WholeProgramOptimization**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, umožňuje optimalizace celého programu.  
  
     Další informace najdete v tématu [/GL (optimalizace celého programu)](/cpp/build/reference/gl-whole-program-optimization).  
  
-   **XMLDocumentationFileName**  
  
     Volitelné `String` parametr.  
  
     Určuje název generované soubory dokumentace XML. Tento parametr může být název souboru nebo adresáře.  
  
     Další informace najdete v tématu `name` argument [/DOC (zpracování dokumentačních komentářů) (C/C++)](/cpp/build/reference/doc-process-documentation-comments-c-cpp). Viz také **GenerateXMLDocumentationFiles** parametr v této tabulce.  
  
-   **MinimalRebuildFromTracking**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, se provádí sledovaných přírůstkové sestavení; Pokud `false`, se provádí opětovném sestavení.  
  
-   **TLogReadFiles**  
  
     Volitelné `ITaskItem[]` parametr.  
  
     Určuje pole položek, které představují *čtení souboru sledování protokoly*.  
  
     Sledování pro čtení souboru protokolu (.tlog) obsahuje názvy vstupní soubory, které jsou přečteny úlohu a je používána systém sestavení projektu pro podporu přírůstkové sestavení. Další informace najdete v tématu **TrackerLogDirectory** a **TrackFileAccess** parametry v této tabulce.  
  
-   **TLogWriteFiles**  
  
     Volitelné `ITaskItem[]` parametr.  
  
     Určuje pole položek, které představují *zápis souboru sledování protokoly*.  
  
     Protokol sledování zápisu souborů (.tlog) obsahuje názvy výstupní soubory, které jsou zapsány úlohou a je používána systém sestavení projektu pro podporu přírůstkové sestavení. Další informace najdete v tématu **TrackerLogDirectory** a **TrackFileAccess** parametry v této tabulce.  
  
-   **TrackFileAccess**  
  
     Volitelné `Boolean` parametr.  
  
     Pokud `true`, sleduje vzory přístupu k souboru.  
  
     Další informace najdete v tématu **TLogReadFiles** a **TLogWriteFiles** parametry v této tabulce.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)