---
title: IntelliTest referenční příručce | Nástroje pro vývojáře společnosti Microsoft Test
ms.date: 05/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest Reference Manual, IntelliTest
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: f9534668ef5cf07388d6eefec9ef37a28593daaa
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="intellitest-reference-manual"></a>IntelliTest referenční příručce

## <a name="contents"></a>Obsah

* **[Přehled IntelliTest](introduction.md)**
  - [Hello World z IntelliTest](introduction.md#the-hello-world-of-intellitest)
  - [Omezení](introduction.md#limitations)
    * [Nondeterminism](introduction.md#nondeterminism)
    * [Souběžnost](introduction.md#concurrency)
    * [Nativní kód](introduction.md#native-code)
    * [Platforma](introduction.md#platform)
    * [Jazyk](introduction.md#language)
    * [Symbolický reasoning](introduction.md#symbolic-reasoning)
    * [Trasování zásobníku nesprávný](introduction.md#incorrect-stack-traces)
  - [Další čtení](introduction.md#further-reading)<p>&nbsp;</p>

* **[Začínáme s IntelliTest](getting-started.md)**
  - [Důležité atributy](getting-started.md#important-attributes)
  - [Důležité statické pomocné třídy](getting-started.md#helper-classes)<p>&nbsp;</p>

* **[Generování testů](test-generation.md)**
  - [Test generátory](test-generation.md#test-generators)
  - [Parametrizované testování částí](test-generation.md#parameterized-unit-testing)
  - [Obecné parametrizované testování částí](test-generation.md#generic-parameterized)
  - [Povolení výjimek](test-generation.md#allowing-exceptions)
  - [Testování interní typy](test-generation.md#internal-types)
  - [Předpoklady a kontrolní výrazy](test-generation.md#assumptions-and-assertions)
  - [Předběžnou podmínku.](test-generation.md#precondition)
  - [Koncová podmínka](test-generation.md#postcondition)
  - [Selhání při testu](test-generation.md#test-failures)
  - [Instalační program a přerušit](test-generation.md#setup-teardown)
  - [Další čtení](test-generation.md#further-reading)<p>&nbsp;</p>

* **[Vstupní generování](input-generation.md)**
  - [Řešitel omezení](input-generation.md#constraint-solver)
  - [Pokrytí kódu dynamické](input-generation.md#dynamic-code-coverage)
  - [Celá čísla a obtékaných objektů](input-generation.md#integers-and-floats)
  - [Objekty](input-generation.md#objects)
  - [Vytváření instancí existujících tříd](input-generation.md#existing-classes)
  - [Viditelnost](input-generation.md#visibility)
  - [Parametrizované mocks](input-generation.md#parameterized-mocks)
  - [Struktury](input-generation.md#structs)
  - [Pole a řetězce](input-generation.md#arrays-and-strings)
  - [Získání dalších vstupy](input-generation.md#additional-inputs)
  - [Další čtení](input-generation.md#further-reading)<p>&nbsp;</p>

* **[Zkoumání hranice](exploration-bounds.md)**
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
  - [TestEmissionBranchHits](exploration-bounds.md#testemissionbranchhits)<p>&nbsp;</p>

* **[Atribut Glosář](attribute-glossary.md)**
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
  - [PexAllowedExceptionFromTypeUnderTest](attribute-glossary.md#pexallowedexceptionfromtypeundertest)<p>&nbsp;</p>

* **[Nastavení vodopádu](settings-waterfall.md)**

* **[Statické pomocné třídy](static-helper-classes.md)**
  - [PexAssume](static-helper-classes.md#pexassume)
  - [PexAssert](static-helper-classes.md#pexassert)
  - [PexChoose](static-helper-classes.md#pexchoose)
  - [PexObserve](static-helper-classes.md#pexobserve)
  - [PexSymbolicValue](static-helper-classes.md#pexsymbolicvalue)<p>&nbsp;</p>

* **[Upozornění a chyb](warnings-and-errors.md)**
  - [MaxBranches překročen](warnings-and-errors.md#maxbranches-exceeded)
  - [MaxConstraintSolverTime překročen](warnings-and-errors.md#maxconstraintsolvertime-exceeded)
  - [MaxConditions překročen](warnings-and-errors.md#maxconditions-exceeded)
  - [MaxCalls překročen](warnings-and-errors.md#maxcalls-exceeded)
  - [MaxStack překročen](warnings-and-errors.md#maxstack-exceeded)
  - [MaxRuns překročen](warnings-and-errors.md#maxruns-exceeded)
  - [MaxRunsWithoutNewTests překročen](warnings-and-errors.md#maxrunswithoutnewtests-exceeded)
  - [Nelze upřesnění řešení](warnings-and-errors.md#cannot-concretize-solution)
  - [Potřebujete pomoc při sestavování objektu](warnings-and-errors.md#help-construct)
  - [Potřebujete další pomoc k vyhledání typů](warnings-and-errors.md#help-types)
  - [Použitelné typ uhádnout](warnings-and-errors.md#usable-type-guessed)
  - [Neočekávaná chyba při zkoumání](warnings-and-errors.md#unexpected-exploration)
  - [Targetinvocationexception –](warnings-and-errors.md#targetinvocationexception)
  - [Uninstrumented metodu s názvem](warnings-and-errors.md#uninstrumented-method-called)
  - [Externí metodu s názvem](warnings-and-errors.md#external-method-called)
  - [Uninstrumentable metodu s názvem](warnings-and-errors.md#uninstrumentable-method-called)
  - [Testovatelnosti problém](warnings-and-errors.md#testability-issue)
  - [Omezení](warnings-and-errors.md#limitation)
  - [Neshoda zjištěnou volání](warnings-and-errors.md#observed-call-mismatch)
  - [Hodnota uložená v statické pole](warnings-and-errors.md#value-static-field)<p>&nbsp;</p>

## <a name="got-feedback"></a>Zpětné vazby máte?

Vystavení vašich nápadů a funkce požadavky na  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
