---
title: Úloha ClangCompile | Dokumentace Microsoftu
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.clangcompile
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), ClangCompile task
- ClangCompile task (MSBuild (Visual C++))
author: mikeblome
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: 218ef07fa3b086a2240362011067bf526088d1f4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62569703"
---
# <a name="clangcompile-task"></a>ClangCompile úkolu

Zabalí nástroj kompilátoru Visual C++ clang.exe.

## <a name="parameters"></a>Parametry

Následující tabulka popisuje parametry **ClangCompile** úloh.

|Parametr|Popis|
|---------------|-----------------|
|**AdditionalIncludeDirectories**|Volitelné **string []** parametru.<br/><br/>Určuje jeden nebo více adresářů, které chcete přidat do cesty zahrnutí; oddělte středníkem, pokud více než jeden.<br/><br/>Použití `-I[path]`.|
|**AdditionalOptions**|Volitelné **řetězec** parametru.|
|**BufferSecurityCheck**|Volitelné **řetězec** parametru.<br/><br/>Kontrola zabezpečení pomáhá odhalit vyrovnávací paměti na zásobníku typu over-pass-the útoku na zabezpečení programu. <br/><br/>Použití `fstack-protector`.|
|**BuildingInIde**|Volitelné **bool** parametru.|
|**CLanguageStandard**|Volitelné **řetězec** parametru.<br/><br/>Určuje standard jazyka C.<br/><br/>Použití `std=[value]` s hodnotou **c89**, **c99**, **c11**, **gnu99**, nebo **gnu11**.|
|**ClangVersion**|Volitelné **řetězec** parametru.|
|**CompileAs**|Volitelné **řetězec** parametru.<br/><br/>Vyberte možnost jazyka kompilace pro soubory .c a .cpp. Výchozí rozpozná na základě přípony .c nebo .cpp rozšíření.<br/><br/>Použití `-x c`, `-x c++`.|
|**CppLanguageStandard**|Volitelné **řetězec** parametru.<br/><br/>Určuje standard jazyka C++.<br/><br/>Použití `std=[value]` s hodnotou **c ++ 98**, **c ++ 11**, **c ++ 1y**, **gnu ++ 98**, **gnu ++ 11**, nebo **gnu ++ 1y**.|
|**DataLevelLinking**|Volitelné **bool** parametru.<br/><br/>Umožňuje, aby optimalizace linkeru odebraly nepoužívaná data generováním jednotlivých datových položek v samostatných oddílech.|
|**DebugInformationFormat**|Volitelné **řetězec** parametru.<br/><br/>Určuje typ ladicích informací generovaných kompilátorem.<br/><br/>**Žádný**, nevytváří žádné ladicí informace, takže kompilace může být rychlejší (použijte `g0`).<br/>**FullDebug**, generovat ladicí informace DWARF2 (použijte `g2 -gdwarf-2`).<br/>**Číslo řádku**, generovat jenom informace o číslech řádků (použijte `gline-tables-only`).|
|**EnableNeonCodegen**|Volitelné **bool** parametru.<br/><br/>Umožňuje generování kódu pro bod hardware s plovoucí desetinnou čárkou NEON. To platí jenom pro architekturu arm.|
|**ExceptionHandling**|Volitelné **řetězec** parametru.<br/><br/>Určuje model zpracování výjimek pro použití kompilátorem.<br/><br/>**Zakázané**, zakažte zpracování výjimek (použijte `fno-exceptions`).<br/>**Povolené**, povolení zpracování výjimek (použijte `fexceptions`).<br/>**UnwindTables**, generuje všechna potřebná statická data, ale nemá vliv na kód generovaný (použijte `funwind-tables`).|
|**FloatABI**|Volitelné **řetězec** parametru.<br/><br/>Výběr možností výběru z ABI s plovoucí desetinnou.<br/><br/>**obnovitelné**, způsobí, že kompilátor bude generovat výstup obsahující volání knihoven pro operace s plovoucí desetinnou čárkou (použijte `mfloat-abi=soft`).<br/>**softfp**, umožňuje generování kódu pomocí hardwarových instrukcí s plovoucí desetinnou čárkou, ale stále používá konvence volání využitím (použijte `mfloat-abi=softfp`).<br/>**pevné**, umožňuje generování instrukcí s plovoucí desetinnou čárkou a používá konvence volání specifických pro FPU (použijte `mfloat-abi=hard`).|
|**ForcedIncludeFiles**|Volitelné **string []** parametru.<br/><br/>jeden nebo více vynucených k zahrnutí souborů.<br/><br/>Použití `-include [name]`.|
|**FunctionLevelLinking**|Volitelné **bool** parametru.<br/><br/>Umožňuje kompilátoru vytvořit balíček individuálních funkcí ve formě zabalených funkcí (sekvence Comdat). Vyžaduje se pro úpravy a pokračovat v práci.<br/><br/>Použití `ffunction-sections`.|
|**GccToolChain**|Volitelné **řetězec** parametru.<br/><br/>Cesta ke složce řetězce nástroje Gcc.|
|**GNUMode**|Volitelné **bool** parametru.<br/><br/>|
|**MSCompatibility**|Volitelné **bool** parametru.<br/><br/>Povolte úplnou kompatibilitu s Microsoft Visual C++.|
|**MSCompatibilityVersion**|Volitelné **řetězec** parametru.<br/><br/>Tečkou oddělená hodnota představuje číslo verze kompilátoru Microsoftu se oznamuje v _MSC_VER (0 = nedefinovat (výchozí)).|
|**MSExtensions**|Volitelné **bool** parametru.<br/><br/>Přijměte některé nestandardní konstrukce podporované kompilátorem Microsoftu.|
|**MSCompilerVersion**|Volitelné **řetězec** parametru.<br/><br/>Číslo verze kompilátoru Microsoftu, které se oznamuje v _MSC_VER (0 = nedefinovat (výchozí)).|
|**MSVCErrorReport**|Volitelné **bool** parametru.<br/><br/>Oznamovat chyby, které Visual Studio můžete použít k analýze souboru a řádku informace.|
|**ObjectFileName**|Volitelné **řetězec** parametru.<br/><br/>Určuje název, který má přepsat výchozí název souboru objektů; může být název souboru nebo adresáře.<br/><br/>Použití `/Fo[name]`.|
|**OmitFramePointers**|Volitelné **bool** parametru.<br/><br/>Zakazuje vytváření ukazatelů na rámce v zásobníku volání.|
|**Optimalizace**|Volitelné **řetězec** parametru.<br/><br/>Určuje úroveň optimalizace pro aplikaci.<br/><br/>**Vlastní**, vlastní optimalizace.<br/>**Zakázané**, zakázat optimalizace (použijte `O0`).<br/>**MinSize**, optimalizovat pro velikost (použijte `Os`).<br/>**MaxSpeed**, optimalizovat rychlost (použijte `O2`).<br/>**Úplné**, nákladné optimalizace (použijte `O3`).|
|**PositionIndependentCode**|Volitelné **bool** parametru.<br/><br/>Generovat pozice nezávislý kód (PIC) pro použití ve sdílené knihovně.|
|**PrecompiledHeader**|Volitelné **řetězec** parametru.<br/><br/>Umožňuje během sestavování nebo použít předkompilovanou hlavičku.|
|**PrecompiledHeaderFile**|Volitelné **řetězec** parametru.<br/><br/>Určuje název hlavičkového souboru pro soubor předkompilované hlavičky. Tento soubor bude rovněž přidán do **vynucené vložených souborů** během sestavování.|
|**PrecompiledHeaderOutputFileDirectory**|Volitelné **řetězec** parametru.<br/><br/>Určuje adresář pro vygenerované předkompilované hlavičky. Tento adresář se také přidá do **další adresáře souborů k zahrnutí** během sestavování.|
|**PrecompiledHeaderCompileAs**|Volitelné **řetězec** parametru.<br/><br/>Vyberte možnost jazyka kompilace pro soubor předkompilované hlavičky.<br/><br/>Použití `-x c-header`, `-x c++-header`.|
|**PreprocessorDefinitions**|Volitelné **string []** parametru.<br/><br/>Definuje symboly předzpracování pro zdrojový soubor.<br/><br/>Použití `-D`.|
|**RuntimeLibrary**|Volitelné **řetězec** parametru.<br/><br/>Určuje knihovnu prostředí runtime pro propojení.<br/><br/>Použití `MSVC /MT`, `/MTd`, `/MD`, `/MDd` přepínače.<br/><br/>**Vícevláknové**, způsobí, že aplikace použije vícevláknovou statickou verzi knihovny run-time.<br/>**MultiThreadedDebug**, definuje _DEBUG a _MT. Tento parametr navíc způsobí, že kompilátor umístí knihovnu s názvem LIBCMTD.lib do souboru .obj, aby linker použil k překladu externích symbolů soubor LIBCMTD.lib.<br/>**MultiThreadedDLL**, způsobí, že aplikace použije vícevláknovou a knihovny DLL konkrétní verzi knihovny run-time. Definuje _MT a _DLL a způsobí, že kompilátor umístí knihovnu s názvem MSVCRT.lib do souboru .obj.<br/>**MultiThreadedDebugDLL**, definuje _DEBUG, _MT a _DLL a způsobí, že aplikace použije ladicí Vícevláknová a knihovny DLL konkrétní verze knihovny run-time. Navíc způsobí, že kompilátor umístí knihovnu s názvem MSVCRTD.lib do souboru .obj.|
|**RuntimeTypeInfo**|Volitelné **bool** parametru.<br/><br/>Přidává kód pro kontrolu typů objektů jazyka C++ za běhu (informace typu za běhu).<br/><br/>Použití `frtti`, `fno-rtti`.|
|**ShowIncludes**|Volitelné **bool** parametru.<br/><br/>Generuje seznam vložených souborů s výstupem kompilátoru.<br/><br/>Použití `-H`.|
|**Zdroje**|Vyžaduje **[] ITaskItem** parametru.|
|**StrictAliasing**|Volitelné **bool** parametru.<br/><br/>Předpokládejme nejpřísnější pravidla pro aliasy. Objekt jednoho typu se nikdy být předpokládat, že na stejné adrese jako objekt jiného typu.|
|**Sysroot**|Volitelné **řetězec** parametru.<br/><br/>Cesta ke složce kořenového adresáře pro hlavičkové soubory a knihovny.|
|**TargetArch**|Volitelné **řetězec** parametru.<br/><br/>Cílová architektura.|
|**ThumbMode**|Volitelné **řetězec** parametru.<br/><br/>Generovat kód, který spouští pro mikroarchitekturu thumb. To platí jenom pro architekturu arm.<br/><br/>**Jezdec**, generuje kód pro Thumb (použijte `mthumb`).<br/>**ARM**, generuje kód pro Arm (použijte `marm`).<br/>**Zakázané**, možnost není k dispozici pro zvolenou platformu.|
|**TrackerLogDirectory**|Volitelné **řetězec** parametru.<br/><br/>Adresář protokolu sledovacího modulu.|
|**TreatWarningAsError**|Volitelné **bool** parametru.<br/><br/>Zpracuje všechna upozornění kompilátoru jako chyby.<br/><br/>Pro nový projekt, může být vhodné použít `/WX` při všech kompilacích; vyřešením všech upozornění zajistíte nejmíň vad kódu možné obtížné najít.|
|**UndefinePreprocessorDefinitions**|Volitelné **string []** parametru.<br/><br/>Určuje že jeden nebo více nedefinovaných hodnot preprocesoru.<br/><br/>Použití `-U [macro]`.|
|**UndefineAllPreprocessorDefinitions**|Volitelné **bool** parametru.<br/><br/>Zruší definici všech dříve definovaných hodnot preprocesoru.<br/><br/>Použití `-undef`.|
|**UseMultiToolTask**|Volitelné **bool** parametru.<br/><br/>Kompilace s využitím více procesorů.|
|**UseShortEnums**|Volitelné **bool** parametru.<br/><br/>Typ výčtu bude používat jenom tolik bajtů vyžaduje vstupní sada možných hodnot.|
|**Verbose**|Volitelné **bool** parametru.<br/><br/>Zobrazit příkazy ke spuštění a používají podrobný výstup.|
|**WarningLevel**|Volitelné **řetězec** parametru.<br/><br/>Vyberte, jak přísně má kompilátor, aby se informace o kódu chyby. Další příznaky se přidávají přímo do **další možnosti** (se `/w`, `/Weverything`).<br/><br/>**TurnOffAllWarnings**, vypne všechna upozornění kompilátoru (použijte `w`).<br/>**EnableAllWarnings**, povolí všechna upozornění včetně těch, které ve výchozím nastavení zakázáno (použijte `Wall`).|

## <a name="see-also"></a>Viz také:

[Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)