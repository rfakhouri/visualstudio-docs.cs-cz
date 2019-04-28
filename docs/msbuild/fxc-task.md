---
title: Úloha FXC | Dokumentace Microsoftu
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.fxc
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), FXC task
- FXC task (MSBuild (Visual C++))
author: mikeblome
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: 65819f1625477effab024055828301b26ab5804a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62931484"
---
# <a name="fxc-task"></a>FXC úkolu

Pomocí kompilátoru shaderu HLSL v procesu sestavení.

## <a name="parameters"></a>Parametry

Následující tabulka popisuje parametry **FXC** úloh.

|Parametr|Popis|
|---------------|-----------------|
|**AdditionalIncludeDirectories**|Volitelné **string []** parametru.<br/><br/>Určuje jeden nebo více adresářů, které chcete přidat do cesty zahrnutí; oddělte středníkem, pokud více než jeden.<br/><br/>Použití `/I[path]`.|
|**AdditionalOptions**|Volitelné **řetězec** parametru.|
|**AllResourcesBound**|Volitelné **bool** parametru.<br/><br/>Kompilátor bude předpokládat, že všechny prostředky, které může shader odkazovat jsou vázána a jsou v dobrém stavu po dobu trvání spouštění shaderu. Dostupné pro Shader Model 5.1 a novější.<br/><br/>Použití `/all_resources_bound`.|
|**AssemblerOutput**|Volitelné **řetězec** parametru.<br/><br/>Určuje obsah výstupního souboru jazyka assembleru.<br/><br/>Použití `/Fc, /Fx`.<br/><br/>**NoListing**<br/>**AssemblyCode**, použijte `Fc`.<br/>**AssemblyCodeAndHex**, použijte `Fx`.|
|**AssemblerOutputFile**|Volitelné **řetězec** parametru.<br/><br/>Určuje název souboru pro souboru výpisu kódu sestavení.|
|**CompileD2DCustomEffect**|Volitelné **bool** parametru.<br/><br/>Kompilovat vlastní efekt Direct2D, který obsahuje pixel shadery. Nepoužívejte pro vrchol nebo výpočet vlastního efektu.|
|**ConsumeExportFile**|Volitelné **řetězec** parametru.|
|**DisableOptimizations**|Volitelné **bool** parametru.<br/><br/>Zakáže optimalizace.<br/><br/>`/Od` zahrnuje `/Gfp` ale výstup nemusí být stejný jako `/Od /Gfp`.|
|**EnableDebuggingInformation**|Volitelné **bool** parametru.<br/><br/>Povolte ladicí informace.|
|**EnableUnboundedDescriptorTables**|Volitelné **bool** parametru.<br/><br/>Informuje kompilátor, že shader může obsahovat deklaraci pole zdrojů s neomezeným rozsahem. Dostupné pro Shader Model 5.1 a novější.<br/><br/>Použití `/enable_unbounded_descriptor_tables`.|
|**EntryPointName**|Volitelné **řetězec** parametru.<br/><br/>Určuje název vstupního bodu pro shader.<br/><br/>Použití `/E[name]`.|
|**GenerateExportFile**|Volitelné **řetězec** parametru.|
|**GenerateExportShaderProfile**|Volitelné **řetězec** parametru.|
|**HeaderFileOutput**|Volitelné **řetězec** parametru.<br/><br/>Určuje název hlavičkového souboru obsahujícího objektový kód.<br/><br/>Použití `/Fh [name]`.|
|**ObjectFileOutput**|Volitelné **řetězec** parametru.<br/><br/>Určuje název objektu souboru.<br/><br/>Použití `/Fo [name]`.|
|**PreprocessorDefinitions**|Volitelné **string []** parametru.<br/><br/>Definuje symboly předzpracování pro zdrojový soubor.|
|**SetRootSignature**|Volitelné **řetězec** parametru.<br/><br/>Připojí kořenový podpis k hodnota bytecode funkce shader. Dostupné pro Shader Model 5.0 a vyšším.<br/><br/>Použití `/setrootsignature`.|
|**ShaderModel**|Volitelné **řetězec** parametru.<br/><br/>Určuje model shaderu. Některé typy shaderů jde použít jenom s novějšími modely shaderů.<br/><br/>Použití `/T [type]_[model]`.|
|**ShaderType**|Volitelné **řetězec** parametru.<br/><br/>Určuje typ shaderu.<br/><br/>Použití `/T [type]_[model]`.<br/><br/>**Efekt**, použijte `fx`.<br/>**Vrchol**, použijte `vs`.<br/>**Pixel**, použijte `ps`.<br/>**Geometrie**, použijte `gs`.<br/>**Trupu**, použijte `hs`.<br/>**Domény**, použijte `ds`.<br/>**COMPUTE**, použijte `cs`.<br/>**Knihovna**, použijte `lib`.<br/>**RootSignature**, generovat objekt kořenového podpisu.|
|**Zdroj**|Vyžaduje **ITaskItem** parametru.|
|**SuppressStartupBanner**|Volitelné **bool** parametru.<br/><br/>Potlačí zobrazení nápisu a informačních zpráv při spuštění.<br/><br/>Použití `/nologo`.|
|**TrackerLogDirectory**|Volitelné **řetězec** parametru.|
|**TreatWarningAsError**|Volitelné **bool** parametru.<br/><br/>Zpracuje všechna upozornění kompilátoru jako chyby.<br/><br/>Pro nový projekt, může být vhodné použít `/WX` při všech kompilacích; vyřešením všech upozornění zajistíte nejmíň vad kódu možné obtížné najít.|
|**VariableName**|Volitelné **řetězec** parametru.<br/><br/>Určuje název proměnné v hlavičkovém souboru.<br/><br/>Použití `/Vn [name]`.|

## <a name="see-also"></a>Viz také:

[Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)