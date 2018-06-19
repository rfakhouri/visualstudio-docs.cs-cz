---
title: Clang vlastnosti projektu (Android C++) | Microsoft Docs
ms.custom: ''
ms.date: 10/23/2017
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 663140ea-a568-472b-a79a-dfea8818e06a
author: corob
ms.author: mblome
manager: douge
f1_keywords:
- VC.Project.VCClangCompilerTool.AdditionalIncludeDirectories
- VC.Project.VCClangCompilerTool.DebugInformationFormat
- VC.Project.VCClangCompilerTool.ObjectFile
- VC.Project.VCClangCompilerTool.WarningLevel
- VC.Project.VCClangCompilerTool.WarnAsError
- VC.Project.VCClangCompilerTool.Verbose
- VC.Project.VCClangCompilerTool.Optimization
- VC.Project.VCClangCompilerTool.StrictAliasing
- VC.Project.VCClangCompilerTool.OmitFramePointers
- VC.Project.VCClangCompilerTool.ExceptionHandling
- VC.Project.VCClangCompilerTool.EnableFunctionLevelLinking
- VC.Project.VCClangCompilerTool.DataLevelLinking
- VC.Project.VCClangCompilerTool.DataLevelLinking
- VC.Project.VCClangCompilerTool.FloatABI
- VC.Project.VCClangCompilerTool.BufferSecurityCheck
- VC.Project.VCClangCompilerTool.PIC
- VC.Project.VCClangCompilerTool.UseShortEnums
- VC.Project.VCClangCompilerTool.RuntimeTypeInfo
- VC.Project.VCClangCompilerTool.CLanguageStandard
- VC.Project.VCClangCompilerTool.CppLanguageStandard
- VC.Project.VCClangCompilerTool.PreprocessorDefinitions
- VC.Project.VCClangCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCClangCompilerTool.UndefineAllPreprocessorDefinitions
- VC.Project.VCClangCompilerTool.ShowIncludes
- VC.Project.VCClangCompilerTool.PrecompiledHeader
- VC.Project.VCClangCompilerTool.PrecompiledHeaderFile
- VC.Project.VCClangCompilerTool.PrecompiledHeaderOutputFileDirectory
- VC.Project.VCClangCompilerTool.PrecompiledHeaderCompileAs
- VC.Project.VCClangCompilerTool.CompileAs
- VC.Project.VCClangCompilerTool.ForcedIncludeFiles
- VC.Project.VCClangCompilerTool.MultiProcessorCompilation
- vc.project.AdditionalOptionsPage
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 8a1fd92a41f145e097615bea4434ea80fd592416
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31067529"
---
# <a name="clang-project-properties-android-c"></a>Vlastnosti projektu clang (Android C++)

Vlastnost | Popis | Možnosti
--- | ---| ---
Další zahrnuté adresáře | Určuje jeden nebo více adresáře, které chcete přidat do cesty zahrnutí; oddělit pomocí středníky, pokud je více než jeden. (-I[path]).
Ladění formátu informací | Určuje typ ladicí informace generované kompilátorem. | **Žádný** -vytvoří žádné informace o ladění, takže kompilace může být rychlejší.<br>**Úplné informace o ladění (DWARF2)** -DWARF2 Generovat ladicí informace.<br>**Řádek číslo informace** -pouze informace Generovat číslo řádku.<br>
Název souboru objektů | Určuje název přepsat výchozí název objektu souboru; může být název souboru nebo adresáře. (Nebo Fo[name]).
Úroveň upozornění | Vyberte, jak striktní chcete kompilátoru být o kódu chyby.  Nastavení další příznaky musí být přidaní přímo k další možnosti. (/ w, /Weverything). | **Vypnout všech upozornění** – zakáže všech upozornění kompilátoru.<br>**EnableAllWarnings** -povolí všechny výstrahy, včetně těch, které ve výchozím nastavení zakázaná.<br>
Zpracovávat upozornění jako chyby | Zpracovává všechny kompilátoru upozornění jako chyby. Pro nový projekt může být nejvhodnější použít wdn v všechny kompilace; vyřešení všech upozornění bude zajištěno, že nejmenší počet defektů možné pevný najít kódu.
Povolit podrobné režim | Zobrazit příkazy spouštět a používat podrobný výstup.
Optimalizace | Určuje úroveň optimalizace pro aplikaci. | **Vlastní** – vlastní optimalizace.<br>**Zakázané** -zakázat optimalizace.<br>**Minimální velikost** -optimalizovat pro velikost.<br>**Maximalizovat rychlost** -optimalizovat pro rychlost.<br>**Úplná optimalizace** -nákladné optimalizace.<br>
Striktní aliasy | Předpokládejme nejpřísnějším pravidla pro aliasy.  Objekt jednoho typu se nikdy se předpokládá, že jsou umístěny na stejnou adresu jako objekt jiného typu.
Vynechat ukazatel na rámec | Zakazuje vytváření ukazatelů na rámce v zásobníku volání.
Povolit výjimky jazyka C++ | Určuje model zpracování má být používána kompilátor výjimek. | **Ne** -zakázat zpracování výjimek.<br>**Ano** -povolit zpracování výjimek.<br>**Unwind tabulky** – vygeneruje všechny potřebné statických dat, ale nemá vliv na kód, který vygenerovala.<br>
Povolit propojení na úrovni funkcí | Umožňuje kompilátoru na jednotlivé funkce balíček ve formě zabalené funkce (COMDATs). Je požadována pro upravit a pokračovat v práci.     (oddíly ffunction).
Povolit propojení na úrovni dat | Umožňuje linkeru optimalizace Odeberte nepoužívané data vydat každou položku dat v samostatné části.
Povolit rozšířené SIMD(Neon) | Umožňuje vygenerovat kód pro NEÓNOVÁ plovoucí bodu hardwaru. To platí pro pouze pro architekturu arm.
ABI s plovoucí desetinnou čárkou | Výběr možnost vybrat plovoucí ABI bodu. | **Logicky** -"Soft" způsobí, že kompilátor generovat výstup obsahující knihovny volá pro operace s plovoucí desetinnou čárkou.<br>**SoftFP** – 'SoftFP' umožňuje generování kódu s plovoucí desetinnou čárkou pokynů hardwaru, ale pořád používají konvence volání konfigurace soft-float.<br>**Pevný** -generování alows 'Pevný' s plovoucí desetinnou čárkou pokyny a používá specifické FPU pravidel pro volání.<br>
Kontrola zabezpečení | Kontrola zabezpečení pomáhá zjišťovat zásobníku vyrovnávací překračující, běžné pokus o útoky na zabezpečení programu. (fstack ochrana). | **Zakázat kontrolu zabezpečení** -zakázat kontrolu zabezpečení.<br>**Povolit kontrola zabezpečení** -povolit kontrola zabezpečení. (fstack ochranné zařízení)<br>
Pozice nezávislé kódu | Generovat pozice nezávislé kódu (PIC) pro použití ve sdílené knihovně.
Použít krátký výčty | Typ výčtu využívá jenom tolik bajtů požadovaných ve vstupní sadě možných hodnot.
Povolit informace běhového typu | Přidá kód pro kontrolu typy objektů C++ v době běhu (informace o běhu programu typ).     (frtti, fno rtti)
Jazyk C – Standard | Určuje standard jazyka C. | **Default**<br>**Kompilátorem C89** -Standard kompilátorem C89 Language.<br>**C99** -C99 Language Standard.<br>**C11** -C11 Language Standard.<br>**C99 (GNU dialekt)** -C99 Standard Language (GNU dialekt).<br>**C11 (GNU dialekt)** -C11 Standard Language (GNU dialekt).<br>
Standard jazyka C++ | Určuje standard jazyka C++. | **Default**<br>**C ++ 03** -03 jazyk standardu C ++.<br>**C ++ 11** -C ++ 11 jazyk Standard.<br>**C ++ 14** -C ++ 14 jazyk Standard.<br>**C ++ 03 (GNU dialekt)** – C ++ 03 Standard Language (GNU dialekt).<br>**C ++ 11 (GNU dialekt)** – C ++ 11 Standard Language (GNU dialekt).<br>**C ++ 14 (GNU dialekt)** – C ++ 14 Standard Language (GNU dialekt).<br>
Definice preprocesoru | Definuje předběžného zpracování symboly pro zdrojový soubor. (-D)
Nedefinované Definice preprocesoru | Určuje, že jeden nebo více preprocesor undefines.  (-U [makro])
Nedefinované všechny definice preprocesoru | Nedefinované všechny dříve definované preprocesoru hodnoty.  (-undef)
Obsahuje zobrazení | Vygeneruje seznam zahrnout soubory s výstupu kompilátoru.  (-H).
Předkompilovaných hlaviček | Vytvoření nebo použití předkompilovaných hlaviček: umožňuje vytvoření nebo použití předkompilovaných hlaviček během sestavení. | **Použití** -použití předkompilovaných hlaviček.<br>**Nepoužívat předkompilované hlavičky** – bez použití předkompilovaných hlaviček.<br>
Předkompilovaný hlavičkový soubor | Určuje název hlavičky souboru pro soubor předkompilovaných hlaviček. Tento soubor bude také přidat do 'musí obsahovat soubory během vytváření sestavení
Adresář souboru výstup předkompilovaných hlaviček | Určuje adresář pro generovaný předkompilovaných hlaviček. Tento adresář také přidá, další adresáře Include' během vytváření sestavení
Kompilace předkompilovaných hlaviček jako | Vyberte kompilace jazyka pro předkompilovaný hlavičkový soubor (- c hlavičky x - x c ++ – hlavička). | **Kompilace jako kód C** -zkompilovat jako C – kód jazyka.<br>**Kompilace jako C++ – kód** -zkompilovat jako C++ – kód.<br>
Kompilace jako | Vyberte možnost kompilace jazyka .c a sada souborů.  "Výchozí" zjistí na základě .c nebo sada rozšíření. (-x - x c, c ++) | **Výchozí** -výchozí.<br>**Kompilace jako kód C** -zkompilovat jako C – kód jazyka.<br>**Kompilace jako C++ – kód** -zkompilovat jako C++ – kód.<br>
Vynutit vložené soubory | jeden nebo více vynutit zahrnout soubory.     (-zahrnují [name])
Kompilace více procesorů | Kompilace více procesorů.
Další možnosti | Další možnosti.
