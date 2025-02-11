---
title: XSD – úloha | Dokumentace Microsoftu
ms.date: 06/27/2018
ms.topic: reference
f1_keywords:
- vc.task.xsd
- VC.Project.VCXMLDataGeneratorTool.Namespace
- VC.Project.VCXMLDataGeneratorTool.GenerateFromSchema
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- XSD task (MSBuild (Visual C++))
- MSBuild (Visual C++), XSD task
ms.assetid: 15c99f5c-7124-4bbc-bc03-70c7bcce8893
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f6e96325edd3a17a09437e093590cc02a55504a5
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67825819"
---
# <a name="xsd-task"></a>XSD – úloha
Zabalí nástroj definici schématu XML (*xsd.exe*), který generuje schématu nebo třída soubory ze zdroje.

> [!NOTE]
> Spouští se v sadě Visual Studio 2017, projekt C++ podporu pro *xsd.exe* je zastaralý. Můžete dál používat **Microsoft.VisualC.CppCodeProvider** rozhraní API tak, že ručně přidáte *CppCodeProvider.dll* do mezipaměti GAC.

## <a name="parameters"></a>Parametry
 Následující tabulka popisuje parametry **XSD** úloh.

- **AdditionalOptions**

     Volitelné **řetězec** parametru.

     Seznam možností, jak je uvedeno na příkazovém řádku. Třeba /\<možnost1 > /\<možnost2 > /\<možnost #>. Tento parametr použijte k určení možností, které nejsou reprezentovány jakýkoli jiný **XSD** parametr úlohy.

- **GenerateFromSchema**

  Volitelné **řetězec** parametru.

  Určuje typy, které se generují z určené schéma.

  Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnost XSD.

  - **třídy** -   **/třídy**

  - **dataset** -  **/dataset**

- **Jazyk**

     Volitelné **řetězec** parametru.

     Určuje programovací jazyk pro použití generovaného kódu.

     Vyberte si z **CS** (C#, což je výchozí hodnota), **VB** (Visual Basic), nebo **JS** (JScript). Můžete také zadat plně kvalifikovaný název pro třídu, která implementuje `System.CodeDom.Compiler.CodeDomProvider Class`.

- **Namespace**

     Volitelné **řetězec** parametru.

     Určuje runtime obor názvů pro generovaný typy.

- **Zdroje**

     Vyžaduje `ITaskItem[]` parametru.

     Definuje pole objektů položky nástroje MSBuild zdrojových souborů, které lze používat a, protože ho vygeneroval úlohy.

- **SuppressStartupBanner**

     Volitelné **logická** parametru.

     Pokud `true`, zabraňuje zobrazování čísel zprávu o autorských právech a verze při spuštění úlohy.

- **TrackerLogDirectory**

     Volitelné **řetězec** parametru.

     Určuje adresář protokolu sledovacího modulu.

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)
