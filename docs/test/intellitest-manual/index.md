---
title: IntelliTest referenčním manuálu | Nástroje pro testování Microsoft pro vývojáře
ms.date: 05/02/2017
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest Reference Manual, IntelliTest
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: d7258549b242091737e14e00980447eb48d5e78b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62551590"
---
# <a name="intellitest-reference-manual"></a>IntelliTest referenčním manuálu

## <a name="contents"></a>Obsah

* **[Přehled funkce IntelliTest](introduction.md)**
  - [The Hello World of IntelliTest](introduction.md#the-hello-world-of-intellitest)
  - [Omezení](introduction.md#limitations)
    * [Nondeterminism](introduction.md#nondeterminism)
    * [Souběžnost](introduction.md#concurrency)
    * [Nativní kód](introduction.md#native-code)
    * [Platforma](introduction.md#platform)
    * [Jazyk](introduction.md#language)
    * [Symbolického uvažování](introduction.md#symbolic-reasoning)
    * [Trasování zásobníku nesprávný](introduction.md#incorrect-stack-traces)
  - [Další čtení](introduction.md#further-reading)

* **[Začínáme s IntelliTest](getting-started.md)**
  - [Důležité atributy](getting-started.md#important-attributes)
  - [Třídy statických pomocných rutin důležité](getting-started.md#helper-classes)

* **[Generování testu](test-generation.md)**
  - [Generátory testu](test-generation.md#test-generators)
  - [Parametrizované testování částí](test-generation.md#parameterized-unit-testing)
  - [Obecné parametry testování částí](test-generation.md#generic-parameterized)
  - [Povolení výjimek](test-generation.md#allowing-exceptions)
  - [Testování vnitřní typy](test-generation.md#internal-types)
  - [Předpoklady a kontrolní výrazy](test-generation.md#assumptions-and-assertions)
  - [Předběžné podmínky](test-generation.md#precondition)
  - [Neplatná následná](test-generation.md#postcondition)
  - [Neúspěšné testy](test-generation.md#test-failures)
  - [Nastavení a dovolí](test-generation.md#setup-teardown)
  - [Další čtení](test-generation.md#further-reading)

* **[Vstupní generování](input-generation.md)**
  - [Řešitel omezení](input-generation.md#constraint-solver)
  - [Dynamický kód pokrytí](input-generation.md#dynamic-code-coverage)
  - [Celá čísla a float](input-generation.md#integers-and-floats)
  - [Objekty](input-generation.md#objects)
  - [Vytvoření instance existujících tříd](input-generation.md#existing-classes)
  - [Viditelnost](input-generation.md#visibility)
  - [Parametrizované mocks](input-generation.md#parameterized-mocks)
  - [Struktury](input-generation.md#structs)
  - [Pole a řetězce](input-generation.md#arrays-and-strings)
  - [Získání další vstupy](input-generation.md#additional-inputs)
  - [Další čtení](input-generation.md#further-reading)

* **[Hranice průzkumu](exploration-bounds.md)**
  - [MaxConstraintSolverTime](exploration-bounds.md#maxconstraintsolvertime)
  - [MaxConstraintSolverMemory](exploration-bounds.md#maxconstraintsolvermemory)
  - [MaxBranches](exploration-bounds.md#maxbranches)
  - [MaxCalls](exploration-bounds.md#maxcalls)
  - [MaxStack](exploration-bounds.md#maxstack)
  - [MaxConditions](exploration-bounds.md#maxconditions)
  - [MaxRuns](exploration-bounds.md#maxruns)
  - [MaxRunsWithoutNewTests](exploration-bounds.md#maxrunswithoutnewtests)
  - [MaxRunsWithUniquePaths](exploration-bounds.md#maxrunswithuniquepaths)
  - [MaxExceptions](exploration-bounds.md#maxexceptions)
  - [TestExcludePathBoundsExceeded](exploration-bounds.md#testexcludepathboundsexceeded)
  - [TestEmissionFilter](exploration-bounds.md#testemissionfilter)
  - [TestEmissionBranchHits](exploration-bounds.md#testemissionbranchhits)

* **[Glosář atributů](attribute-glossary.md)**
  - [PexAssumeNotNull](attribute-glossary.md#pexassumenotnull)
  - [PexClass](attribute-glossary.md#pexclass)
  - [PexGenericArguments](attribute-glossary.md#pexgenericarguments)
  - [PexMethod](attribute-glossary.md#pexmethod)
  - [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)
  - [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
  - [PexAssemblyUnderTest](attribute-glossary.md#pexassemblyundertest)
  - [PexInstrumentAssemblyAttribute](attribute-glossary.md#pexinstrumentassemblyattribute)
  - [PexUseType](attribute-glossary.md#pexusetype)
  - [PexAllowedException](attribute-glossary.md#pexallowedexception)
  - [PexAllowedExceptionFromAssembly](attribute-glossary.md#pexallowedexceptionfromassembly)
  - [PexAllowedExceptionFromType](attribute-glossary.md#pexallowedexceptionfromtype)
  - [PexAllowedExceptionFromTypeUnderTest](attribute-glossary.md#pexallowedexceptionfromtypeundertest)

* **[Vodopádové nastavení](settings-waterfall.md)**

* **[Třídy statických pomocných rutin](static-helper-classes.md)**
  - [PexAssume](static-helper-classes.md#pexassume)
  - [PexAssert](static-helper-classes.md#pexassert)
  - [PexChoose](static-helper-classes.md#pexchoose)
  - [PexObserve](static-helper-classes.md#pexobserve)
  - [PexSymbolicValue](static-helper-classes.md#pexsymbolicvalue)

* **[Upozornění a chyby](warnings-and-errors.md)**
  - [MaxBranches překročena](warnings-and-errors.md#maxbranches-exceeded)
  - [MaxConstraintSolverTime exceeded](warnings-and-errors.md#maxconstraintsolvertime-exceeded)
  - [MaxConditions překročena](warnings-and-errors.md#maxconditions-exceeded)
  - [MaxCalls překročena](warnings-and-errors.md#maxcalls-exceeded)
  - [MaxStack překročena](warnings-and-errors.md#maxstack-exceeded)
  - [MaxRuns překročena](warnings-and-errors.md#maxruns-exceeded)
  - [MaxRunsWithoutNewTests překročena](warnings-and-errors.md#maxrunswithoutnewtests-exceeded)
  - [Nejde konkretizovat řešení](warnings-and-errors.md#cannot-concretize-solution)
  - [Potřebuji nápovědu k vytvoření objektu](warnings-and-errors.md#help-construct)
  - [Potřebujete najít typy](warnings-and-errors.md#help-types)
  - [Použitelný typ uhodnout](warnings-and-errors.md#usable-type-guessed)
  - [Neočekávaná chyba při průzkumu](warnings-and-errors.md#unexpected-exploration)
  - [TargetInvocationException](warnings-and-errors.md#targetinvocationexception)
  - [Neinstrumentované metody, které volá](warnings-and-errors.md#uninstrumented-method-called)
  - [Externí metodu s názvem](warnings-and-errors.md#external-method-called)
  - [Neinstrumentovatelné metody, které volá](warnings-and-errors.md#uninstrumentable-method-called)
  - [Problém s testovatelností](warnings-and-errors.md#testability-issue)
  - [Omezení](warnings-and-errors.md#limitation)
  - [Pozorovaná neshoda volání](warnings-and-errors.md#observed-call-mismatch)
  - [Hodnota uložená ve statické pole](warnings-and-errors.md#value-static-field)

## <a name="got-feedback"></a>Máte nějakou zpětnou vazbu?

Publikovat své nápady a funkce na požadavky [komunity vývojářů](https://developercommunity.visualstudio.com/content/idea/post.html?space=8).