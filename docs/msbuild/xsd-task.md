---
title: XSD – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
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
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 77abc3b0d933be0e9677a4d89e0463a5fc7b4926
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="xsd-task"></a>XSD – úloha
Zabalí nástroj definice schématu XML (xsd.exe), který generuje schématu nebo třída soubory ze zdroje.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **XSD** úloh.  
  
-   **AdditionalOptions**  
  
     Volitelné **řetězec** parametr.  
  
     Seznam možností jako zadaného na příkazovém řádku. Například "*/option1 /option2 /option#*". Tento parametr použijte k určení možnosti, které nejsou reprezentovány jakékoliv **XSD** parametr úloh.  
  
-   **GenerateFromSchema**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje typy, které se generují z určené schéma.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá XSD možnost.  
  
    -   **třídy** -   **/třídy**  
  
    -   **dataset** - **/dataset**  
  
-   **Jazyk**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje programovací jazyk, který chcete použít pro generovaný kód.  
  
     Vybírejte z těchto možností **CS** (C#, což výchozí nastavení), **VB** (Visual Basic), nebo **JS** (JScript). Můžete také zadat plně kvalifikovaný název pro třídu, která implementuje `System.CodeDom.Compiler.CodeDomProvider Class`.  
  
-   **obor názvů**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje runtime obor názvů pro generovaný typy.  
  
-   **Zdroje**  
  
     Požadované `ITaskItem[]` parametr.  
  
     Definuje pole MSBuild zdrojového souboru položek, které je možné využívat a vygenerované úlohami.  
  
-   **SuppressStartupBanner**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, zabraňuje zobrazení číslo zprávy o autorských právech a verzi, po spuštění úlohy.  
  
-   **TrackerLogDirectory**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje adresář pro protokol sledovací modul.  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)