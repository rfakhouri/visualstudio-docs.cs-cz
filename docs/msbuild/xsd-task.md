---
title: "XSD – úloha | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "13"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e45350598a50709a411da270e3607197a36ee20b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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
  
    -   **Datová sada** - **/dataset**  
  
-   **Jazyk**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje programovací jazyk, který chcete použít pro generovaný kód.  
  
     Vybírejte z těchto možností **CS** (C#, což výchozí nastavení), **VB** (Visual Basic), nebo **JS** (JScript). Můžete také zadat plně kvalifikovaný název pro třídu, která implementuje `System.CodeDom.Compiler.CodeDomProvider Class`.  
  
-   **Namespace**  
  
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